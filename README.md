
# ANT DESIGN

## Components

## Button
	Types: Primary, dashed, text, link
	Size: Large, Default, Small
### Import
	import { Button } from 'antd';
### Usage
	<Button type="primary" size="large">
          Primary
        </Button>
	
## Button with download icon
	 <Button type="primary" shape="circle" icon={<DownloadOutlined />}  />
         <Button type="primary" shape="round" icon={<DownloadOutlined />}/>
         <Button type="primary" shape="round" icon={<DownloadOutlined />}/>
	 
#### To make a button background tranparent
	 <Button type="primary" ghost>
    	  Primary
    	 </Button>
#### Other propertied on button : disabled, loading, block etc

## AFFIX
  Make something stick to the viewport
  
 	import { Affix, Button } from 'antd';
	<Affix offsetTop={top}>
        <Button type="primary" onClick={() => setTop(top + 10)}>
          Affix top
         </Button>
     	</Affix>
	
## Menu
#### for basic horizontal Menu
	import { Menu } from 'antd';
	<Menu onClick={this.handleClick} selectedKeys={[current]} mode="horizontal">
        <Menu.Item key="mail" icon={<MailOutlined />}>
          Navigation One
        </Menu.Item>
        <Menu.Item key="app" disabled icon={<AppstoreOutlined />}>
          Navigation Two
        </Menu.Item>
	
#### We can include subMenu also
	 <SubMenu icon={<SettingOutlined />} title="Navigation Three - Submenu">
          <Menu.ItemGroup title="Item 1">
            <Menu.Item key="setting:1">Option 1</Menu.Item>
            <Menu.Item key="setting:2">Option 2</Menu.Item>
          </Menu.ItemGroup>
          <Menu.ItemGroup title="Item 2">
            <Menu.Item key="setting:3">Option 3</Menu.Item>
            <Menu.Item key="setting:4">Option 4</Menu.Item>
          </Menu.ItemGroup>
        </SubMenu>
	</Menu>
	
## Pagination
#### Split a long list into several pages

### Basic Pagination
	import { Pagination } from 'antd';
	ReactDOM.render(<Pagination defaultCurrent={1} total={50} />, mountNode);
### Change size of pagination
	<Pagination
     	 showSizeChanger
     	 onShowSizeChange={onShowSizeChange}
     	 defaultCurrent={3}
     	 total={500}
    	/>
	
### Add a quick jumper to certain page
	<Pagination showQuickJumper defaultCurrent={2} total={500} onChange={onChange} />

## Basic Dropdown
	import { Menu, Dropdown } from 'antd';

	const menu = (
 	 <Menu>
    	<Menu.Item>
         <a target="_blank" rel="noopener noreferrer" href="http://www.abc.com/">
         1st menu item
        </a>
   	 </Menu.Item>
   	 <Menu.Item>
    	  <a target="_blank" rel="noopener noreferrer" href="http://www.xyz.com/">
        2nd menu item
        </a>
      	</Menu.Item>
    	
	);
	
	<Dropdown overlay={menu}>
	<a className="ant-dropdown-link" onClick={e => e.preventDefault()}>
	Hover me <DownOutlined />
	</a>
	</Dropdown>

#

## Alert
#### Shows alert messages to users
	import { Alert } from 'antd';

	ReactDOM.render(
 	 <>
  	  <Alert message="Success Text" type="success" />
   	 <Alert message="Info Text" type="info" />
   	 <Alert message="Warning Text" type="warning" />
   	 <Alert message="Error Text" type="error" />
  	</>,
 	 mountNode,
	);
	
## Modals
#### used to interact with users without going to next page
	import { Modal, Button } from 'antd';


 	 render() {
 	   return (
  	    <>
        <Button type="primary" onClick={this.showModal}> //visible true
          Open Modal
        </Button>
        <Modal
          title="Basic Modal"
          visible={this.state.visible}
          onOk={this.handleOk} //visible false
          onCancel={this.handleCancel} //sets visible flase
        >
          <p>Some contents...</p>
          <p>Some contents...</p>
          <p>Some contents...</p>
        </Modal>
    	  </>
   	 );
 	 }
	}
	
#
# Grids
###### Based on 12 Grids System, we divided the design area into 24 sections, for example for a layout like 3 equal divisions of the page we use
	<Col span={8} />.
###### Content should be placed inside <Col>Normal Content</Col> and Columns should be placed inside 
	<Row><Col span={8}/></Row>
###### Example
     <Row>
      <Col span={6}>content</Col>
      <Col span={6}>content</Col>
      <Col span={6}>content</Col>
      <Col span={6}>content</Col>
    </Row>
###### This will divide the page into 4 sections each 6-6 boxes as we have totla of 24 boxes on a page in ant.

### Grid Gutter
###### You can use the gutter property of Row as grid spacing, we recommend set it to (16 + 8n) px. (n stands for natural number.)
###### You can set it to a object like { xs: 8, sm: 16, md: 24, lg: 32 } for responsive design.
###### You can use a array to set vertical spacing, [horizontal, vertical] [16, { xs: 8, sm: 16, md: 24, lg: 32 }].
###### Example
 
## Horizontal->Create horizontal spacing between boxes.
    <Row gutter={16}>
      <Col className="gutter-row" span={6}>
        <div style={style}>col-6</div>
      </Col>
      <Col className="gutter-row" span={6}>
        <div style={style}>col-6</div>
      </Col>
     </Row>
## Responsive->Creates spacing between boxes as per screen sizes.
    <Row gutter={{ xs: 8, sm: 16, md: 24, lg: 32 }}>
      <Col className="gutter-row" span={6}>
        <div style={style}>col-6</div>
      </Col>
      <Col className="gutter-row" span={6}>
        <div style={style}>col-6</div>
      </Col>
    </Row>
## Vertical->Create[{Horizontal,Vertical Spacing}] between grids
    <Row gutter={[16, 24]}>
      <Col className="gutter-row" span={6}>
        <div style={style}>col-6</div>
      </Col>
      <Col className="gutter-row" span={6}>
        <div style={style}>col-6</div>
      </Col>
    </Row>
    

## Column Offset-> Effective to create spaces between grid blocks.
###### Offset can set the column to the right side. For example, using offset = {4} can set the element shifted to the right four columns width.
	<Row>
      <Col span={8}>col-8</Col>
      <Col span={8} offset={8}>
        Comntent
      </Col>
    </Row>
    
###### Explanation->It creates a Block of size 8 and and another box of size 8 but at a space of 8 boxes to the right from the left block.
## Grid sort
###### By using push and pull class you can easily change column order.
	<Row>
    <Col span={18} push={6}>
      col-18 col-push-6
    </Col>
    <Col span={6} pull={18}>
      col-6 col-pull-18
    </Col>
   </Row>,

###### Explanation->First col pushes the 6 size block towards its position and second col pulls the 18 size block towards its position.   
#
# Flex Properties on Grids.
## Using Flex Box On the Parent Elements. Ant design supports all flex properties.
#### Child elements depending on the value of the start,center, end,space-between, space-around, which are defined in its parent node.
#### We can use Align Properties too Vertically. Example-> Align Top, Align Middle, Align Bottom.

# Responsive
###### Referring to the Bootstrap responsive design,here preset six dimensions: xs sm md lg xl.We can place our grid blocks as requires by our screen sizes.


# Layout 
###### Ant design provides layout models which ca be used according to users needs. We can nest layout inside a layout, and the header, content, footer should be placed inside of layout.It provides responsive breakpoint and fixed header and sidebar layouts.
 	<Layout>
      <Header>Header</Header>
      <Content>Content</Content>
      <Footer>Footer</Footer>
    </Layout>

	

         
	



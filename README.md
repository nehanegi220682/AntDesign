
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
# Grids
###### Based on 12 Grids System, we divided the design area into 24 sections, for example for a layout like 3 equal divisions of the page we use <Col span={8} />.
###### Content should be placed inside <Col>Normal Content</Col> and Columns should be placed inside <Row><Col span={8}/></Row>
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
 
## Horizontal -Create horizontal spacing between boxes.
    <Row gutter={16}>
      <Col className="gutter-row" span={6}>
        <div style={style}>col-6</div>
      </Col>
      <Col className="gutter-row" span={6}>
        <div style={style}>col-6</div>
      </Col>
     </Row>
## Responsive-Creates spacing between boxes as per screen sizes.
    <Row gutter={{ xs: 8, sm: 16, md: 24, lg: 32 }}>
      <Col className="gutter-row" span={6}>
        <div style={style}>col-6</div>
      </Col>
      <Col className="gutter-row" span={6}>
        <div style={style}>col-6</div>
      </Col>
    </Row>
## Vertical.Create [{Horizontal,Vertical Spacing}] between grids
    <Row gutter={[16, 24]}>
      <Col className="gutter-row" span={6}>
        <div style={style}>col-6</div>
      </Col>
      <Col className="gutter-row" span={6}>
        <div style={style}>col-6</div>
      </Col>
    </Row>

	

         
	



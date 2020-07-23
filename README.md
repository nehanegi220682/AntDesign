
	
# queries
# count
	db.getCollection('Users').aggregate([
	{$match:{age:{$gte:25}}},
	{$count:"Age_Count"} 
	])


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
         
	



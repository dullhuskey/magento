#Layout 布局文件的日常使用操作

### 产品列表
#### `catalog/product_list`

	<block type="catalog/product_list" name="search_result_list" template="catalog/product/list.phtml">
		<!--
		设置每行显示多少列
		@param 布局类型  empty/one_column/two_columns_left/two_columns_right/three_columns
		@param 显示列数	
		-->
		<action method="addColumnCountLayoutDepend"><layout>empty</layout><count>6</count></action>
		<!--
		设置工具条布局名称
		@param 名称 
		-->
        <action method="setToolbarBlockName"><name>product_list_toolbar</name></action>
		
	</block>

### 产品列表工具条
#### `catalog/product_list_toolbar`
	
	
    <block type="catalog/product_list_toolbar" name="product_list_toolbar" template="catalog/product/list/toolbar.phtml">
		<!-- 
		设置排序规则
		@param 排序规则 desc/asc 
		-->
        <action method="setDefaultDirection"><param>desc</param></action>
		<!--
		设置排序列 
		@param 产品属性名 name/price/position/popular 等等 
		-->
        <action method="setSortBy"><param>popular</param></action>
    </block>

### 分页工具条
#### `page/html_pager`
	
	<block type="page/html_pager" name="product_list_toolbar_pager">
		<!--
		设置List 格式输出每页数量
		@param 数量
		-->
		<action method="setDefaultListPerPage"><limit>4</limit></action>
        <!--
		设置Grid 格式输出每页数量
		@param 数量
		-->
		<action method="setDefaultGridPerPage"><limit>9</limit></action>
		<!--
		添加每页显示数量
		@param 显示模式
		@param 数量或者all
		@param 输出标签
		-->
        <action method="addPagerLimit"><mode>list</mode><limit>2</limit></action>
        <action method="addPagerLimit" translate="label">
				<mode>list</mode>
				<limit>all</limit>
				<label>All</label>
		</action>
	</block>




	
    





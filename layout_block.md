#Layout 布局文件的日常使用操作
    
### 产品list排序
#### Block [`catalog/product_list_toolbar`](block_product_list_toolbar.md)

    <block type="catalog/product_list_toolbar" name="product_list_toolbar" template="catalog/product/list/toolbar.phtml">
        <action method="setDefaultDirection"><param>desc</param></action>
        <action method="setSortBy"><param>popular</param></action>
    </block>
    





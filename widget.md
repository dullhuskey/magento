# Widget

``` 
    class Mage_Adminhtml_Block_Widget_Grid
    /**
     * Add column to grid
     *
     * @param   string $columnId
     * @param   array || Varien_Object $column
     * @return  Mage_Adminhtml_Block_Widget_Grid
     */
    public function addColumn($columnId, $column);
    
    $columId; // 列ID标识
    $colum = array(
      "header" => "标题",
      "index"  => "与collection对应的取值名称",
      "type"   => "列格式类型",
      "width"  => "列显示宽度"    
    )
    
    // normal
    $this->addColumn("price4", array(
    "header" => Mage::helper("pricesystem")->__("Price 50"),
    "index" => "price4",
    ));
    
    // options
    $this->addColumn("manager_updated", array(
      "header" => Mage::helper("pricesystem")->__("ETS Updated"),
      "index" => "manager_updated",
      "type" => "options",
      "options" => array(
                      "0" => "No",
                      "1" => "Yes"
                  )
      ));
    
    
    
    ```
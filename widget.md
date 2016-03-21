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
      "width"  => "列显示宽度",
      "filter"    => false,  // 是否过滤
      "sortable"  => false,  // 是否允许排序
      "is_system" => true,   //是否系统自带
      'renderer' => 'Dullhuskey_Rewrite_Block_Adminhtml_Searchkeywords_Renderer_Image'  // 重新渲染内容
    )
    
    
    //renderer
    
    class Dullhuskey_Rewrite_Block_Adminhtml_Searchkeywords_Renderer_Test extends Mage_Adminhtml_Block_Widget_Grid_Column_Renderer_Abstract{
      public function render(Varien_Object $row)
      {
          return $this->_getValue($row);    // 返回整行的值
      }
      protected function _getValue(Varien_Object $row)
      {
          $val = $row->getData($this->getColumn()->getIndex());
          $out = "Render Test :{$val}";
          return $out;
      }
    }
    
    
    
    // text/default
    $this->addColumn('real_order_id', array(
        'header'=> Mage::helper('sales')->__('Order #'),
        'type'  => 'text',
        'index' => 'o.increment_id',
    ));

    
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
      
     // currency 
    $this->addColumn('grand_total', array(
    'header' => Mage::helper('sales')->__('G.T. (Purchased)'),
    'index' => 'o.grand_total',
    'type'  => 'currency',
    'currency' => 'order_currency_code',
    ));
    
    // number
     $this->addColumn('grand_total', array(
            'header' => Mage::helper('sales')->__('利润率'),
            'index' => 'profit',
            'type'   => 'number'
    ));
    
    // datetime
    $this->addColumn('created_at', array(
            'header' => Mage::helper('sales')->__('Purchased On'),
            'index' => 'o.created_at',
            'type' => 'datetime',
            'width' => '100px',
      ));
      
     // store 
    $this->addColumn('store_id', array(
          'header'    => Mage::helper('sales')->__('Purchased From (Store)'),
          'index'     => 'store_id',
          'type'      => 'store',
          'store_view'=> true,
          'display_deleted' => true,
      ));
      
    // action  
    $this->addColumn('action',
          array(
              'header'    => Mage::helper('sales')->__('Action'),
              'type'      => 'action',
              'getter'     => 'getId',
              'actions'   => array(
                  array(
                      'caption' => Mage::helper('sales')->__('View'),
                      'url'     => array('base'=>'*/sales_order/view'),
                      'field'   => 'order_id'
                  )
              )
      ));
      
     //image 
    $this->addColumn('image',
          array(
              'header'=> Mage::helper('catalog')->__('Image'),
              'type'  => 'image',
              'index' => 'image',
    ));

  
    
    
   
   
   
    
    
    
    ```
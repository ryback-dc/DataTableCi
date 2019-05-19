cara installasi


1. Copy Datatablelibs.php ke dalam folder libraries di codegintier
2. Edit Autoload.php di folder config. lalu tambahakan Datatablelibs di dalam array libraries


cara penggunaan

1. buat sebuah function di controller dengan isi sebagai berikut 

    $table 	        = 'nama_table';
		$primaryKey    = 'primary_key';
    $columns 	  = array(
                         array( 'db' => '`b`.`nama_field`',        'dt' => nomor_urut_table,    'field' => 'nama_field' ),
                         array( 'db' => '`b`.`nama_field`',      'dt' => nomor_urut_table,   'formatter' => function( $d, $row ) {
                                        $return  = 'html Tag';
                                        return $return;
                                }, 'field' => 'nama_field' )                         
							);
                            
			  $joinQuery	 = "FROM `$table` AS `b`";
			  $extraWhere  = "1=1 where query";
			  $groupBy		 = "";
			  $orderBy		 = "";
        $sql_details   = "load nama array database config"
			  echo json_encode(  $this->datatablelibs->simple( $_POST, $sql_details, $table, $primaryKey, $columns, $joinQuery, $extraWhere, $groupBy ,$orderBy ) );

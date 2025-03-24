# Encrypted Stuff
This is some sample data to demonstrate why you shouldn't encrypt with SHA1 or something like old CI code for PHP version 7-ish. The samples are for internal use only.

If you call the built-in base64_decode and then the ecnrypt library  _xor_decode and trace that function you will see a simple xor hash of the value and key. There has to be a hack for this somewhere already.

 
    $input = "BjJTZFNjBmoIPlJjCjNTagYwUmQ=";
    $key = "########################";
    $dec = base64_decode($input);
    $encrypt = $this->ci->load->library("encrypt");
    $result = $encrypt->_xor_decode($dec, $key);
    echo $result;


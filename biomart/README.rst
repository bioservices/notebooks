Get the GENE associated to a specific GO terms (or list of GO terms)
======================================================================

Here is a simple recipe to fetch GENE names (HGNC) associated to a list of GO terms.


::


  from bioservices import BioMart
  s = BioMart()

  s.add_dataset_to_xml('hsapiens_gene_ensembl')
  s.create_attribute('hgnc_symbol')
  s.add_attribute_to_xml('name_1006') # not sure what this is for ?
  s.add_attribute_to_xml('go_id')
  s.add_attribute_to_xml('hgnc_symbol')
  s.add_filter_to_xml('go_id', 'GO:0042542,GO:0007259')
  print s.get_xml()
  print s.query(s.get_xml())

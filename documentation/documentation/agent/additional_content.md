---
layout: page
title: How to push additional content in my inventory
---

# How to push additional content in my inventory

## Additional content

You can use *additional-content* [configuration parameter]({{ baseurl }}/documentation/documentation/agent/configuration.html) 
(alternatively, *--additional-content* [command-line options](man.html)) to inject arbitary XML content into
inventory result.

For instance, to add some manually installed software, unknown from the
packaging system database:

    $> cat /tmp/foo.xml
    <?xml version="1.0" encoding="UTF-8" ?>
    <REQUEST>
      <CONTENT>
          <SOFTWARES>
              <NAME>foo</NAME>
              <VERSION>bar</VERSION>
          </SOFTWARES>
      </CONTENT>
    </REQUEST>
    $> fusioninventory-agent --additional-content /tmp/foo.xml

## Perl module

You can extend FusionInventory by creating a custom Perl module, and installing
it anywhere under 'lib/FusionInventory/Agent/Task/Inventory' directory. It will
be automatically loaded and executed at run time.

Example: <http://forum.fusioninventory.org/viewtopic.php?id=2248> (French)

Installation:
-------------
Be aware that this installation process has been tested on ArchLinux and Ubuntu14.04 for the OSs and Gnome3 and Unity for the DE, so please if you are testing it on other distro and it did work perfectly tell us to update this list, but basically this is the default installation process for any Linux based distro.

All operations will be done as **root**.

1.  Copy the file `symbols/dz` to `/usr/share/X11/xkb/symbols/dz`.
2.  Add `kab              Taqbaylit (KAB)` after `!layout` and 
```
  ber             kab: Berber (Kabylia, Tifinagh characters)
  kab             kab: Latin (Kabylia, Latin characters)
  fr              kab: French (Kabylia)
```
after `! variant` in `/usr/share/X11/xkb/rules/base.lst` and `/usr/share/X11/xkb/rules/evdev.lst`.

3.  Add the following lines inside `<layoutList> ... </layoutList>` in `/usr/share/X11/xkb/rules/base.xml` and `/usr/share/X11/xkb/rules/evdev.xml`:

    ```
    <layout>
      <configItem>
        <name>kab</name>
        <shortDescription>kab</shortDescription>
        <description>Kabylian (Kabylia, Latin characters)</description>
      </configItem>
      <variantList>
        <variant>
          <configItem>
            <name>ber</name>
            <shortDescription>ber</shortDescription>
            <description>Kabylian (Kabylia, Tifinagh characters)</description>
            <languageList>
              <iso639Id>ber</iso639Id>
            </languageList>
          </configItem>
        </variant>
        <variant>
          <configItem>
            <name>french</name>
            <shortDescription>fr</shortDescription>
            <description>French (Kabylia)</description>
            <languageList>
              <iso639Id>fra</iso639Id>
            </languageList>
          </configItem>
        </variant>
      </variantList>
    </layout>
    ```
4.  Restart the Xorg server or your computer.
5.  Now you can find the layout in the keyboard settings of your desktop manager: 
Berber (Kabylia, Tifinagh characters), Latin (Kabylia, Latin characters) or French (Kabylia).

Neue Avatare in den OpenSimulator einbinden aus entpackten IAR Dateien (Ubuntu Linux).
´´´Bash
python3 updatelibrary.py -n "Roth2-v1" -s "Roth2-v1" -a Roth2-v1 -i Roth2-v1
python3 updatelibrary.py -n "Roth2-v2" -s "Roth2-v2" -a Roth2-v2 -i Roth2-v2
python3 updatelibrary.py -n "Ruth2-v3" -s "Ruth2-v3" -a Ruth2-v3 -i Ruth2-v3
python3 updatelibrary.py -n "Ruth2-v4" -s "Ruth2-v4" -a Ruth2-v4 -i Ruth2-v4
´´´

Es werden je 3 Dateien erstellt Beispiel:
´´´Bash
Roth2-v1AssetSet.xml
Roth2-v1InvFolders.xml
Roth2-v1InvItems.xml
´´´

In opensim/bin/assets/AssetSets.xml muss folgendes eingefügt werden:
´´´XML
  <Section Name="Roth2-v1">
    <Key Name="file" Value="Roth2-v1/Roth2-v1AssetSet.xml"/>
	</Section>

	<Section Name="Roth2-v2">
	  <Key Name="file" Value="Roth2-v2/Roth2-v2AssetSet.xml"/>
	</Section>

	<Section Name="Ruth2-v3">
	  <Key Name="file" Value="Ruth2-v3/Ruth2-v3AssetSet.xml"/>
	</Section>

	<Section Name="Ruth2-v4">
	  <Key Name="file" Value="Ruth2-v4/Ruth2-v4AssetSet.xml"/>
	</Section>
 
</Nini>
´´´
´´´Bash
Verzeichnis erstellen: opensim/bin/inventory/Roth2-v1Library
Verzeichnis erstellen: opensim/bin/inventory/Roth2-v2Library
Verzeichnis erstellen: opensim/bin/inventory/Ruth2-v3Library
Verzeichnis erstellen: opensim/bin/inventory/Ruth2-v4Library
´´´
´´´XML
Im opensim/bin/inventory/Libraries.xml muss folgendes eingefügt werden:

  <Section Name="Roth2-v1 Library">
    <Key Name="foldersFile" Value="Roth2-v1Library/Roth2-v1InvFolders.xml"/>
    <Key Name="itemsFile" Value="Roth2-v1Library/Roth2-v1InvItems.xml"/>
  </Section>
  
  <Section Name="Roth2-v2 Library">
    <Key Name="foldersFile" Value="Roth2-v2Library/Roth2-v2InvFolders.xml"/>
    <Key Name="itemsFile" Value="Roth2-v2Library/Roth2-v2InvItems.xml"/>
  </Section>
  
  <Section Name="Ruth2-v3 Library">
    <Key Name="foldersFile" Value="Ruth2-v3Library/Ruth2-v3InvFolders.xml"/>
    <Key Name="itemsFile" Value="Ruth2-v3Library/Ruth2-v3InvItems.xml"/>
  </Section>
  
  <Section Name="Ruth2-v4 Library">
    <Key Name="foldersFile" Value="Ruth2-v4Library/Ruth2-v4InvFolders.xml"/>
    <Key Name="itemsFile" Value="Ruth2-v4Library/Ruth2-v4InvItems.xml"/>
  </Section>
´´´

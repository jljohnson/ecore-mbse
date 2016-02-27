#Common MBSE vocabulary 





##Instructions to use and customize common MBSE vocabulary  

Last updated by Axel Reichwein (axel.reichwein@koneksys.com) 				February 26, 2016


###1.	Downloading the ecore-mbse repository

1. Open the Git Repositories View (Window -> Show View -> type “Git Repositories” in the search field)
2. Click on the Clone Repository icon  
3. In the URI field, paste the following URL: https://github.com/ld4mbse/ecore-mbse.git
4. The Host and Repository fields will autofill.
5. Click Next, only select the master branch
6. Click Next until Finish.

###2.	Importing the edu.gatech.mbsec.ecore.mbse project into the Eclipse workspace

1. In the Git repositories view, right-click edu.gatech.mbsec.triplestore.tdb.clients and select “Import Projects”. Click Next until Finish. The edu.gatech.mbsec.ecore.mbse project will be in the Eclipse workspace.
2. In Eclipse, open the Project Explorer view. (Window → Show View → Project Explorer)

###3.	Customizing the common MBSE vocabulary

1.	In Eclipse, open the Project Explorer view. (Window → Show View → Project Explorer). By default, it is already visible at the left of the screen.
2.	Select the just created edu.gatech.mbsec.ecore.mbse project and expand it
3.	Expand the Ecore Metamodels folder
4.	Open the CommonMBSEVocabulary.ecore file 
5.	In the editor window (in the middle of Eclipse), select the tab corresponding to the CommonMBSEVocabulary.ecore file
6.	Expand the root node with a platform URI 
7.	Expand the mbse node with a platform URI 
8.	Expand the node of your choice to examine the resource types defined in the common MBSE vocabulary. For example, expand the Block node showing that an MBSE block has a name, parameters and ports.
9.	You can customize the MBSE vocabulary by defining additional resource types or changing existing ones.
10.	References from tool-specific adapters to the common MBSE vocabulary are defined in the tool-specific Ecore metamodel. The level to which a tool-specific adapter supports the common MBSE vocabulary is defined in the tool-specific Ecore metamodel.

For example, a Simulink block, as defined in the [simulink4MBSE.ecore](https://github.com/ld4mbse/oslc-adapter-simulink/blob/master/edu.gatech.mbsec.adapter.simulink.ecore/model/simulink4MBSE.ecore) metamodel, has a generalization relationship with the MBSE block defined in the common MBSE vocabulary (line 22 of simulink4MBSE.ecore).
```text
<eClassifiers xsi:type="ecore:EClass" name="Block" eSuperTypes="../../org.eclipse.mbse.common.vocabulary/Ecore%20Metamodels/CommonMBSEVocabulary.ecore#//Block">
```

Note: you can open the .ecore file with various viewers. In order to see the XML representation, you need to right-click on  the file, select Open With->XML Editor. In order to see the tree representation, you need to right-click on  the file, select Open With->Sample Ecore Model Editor

Generalization relationships between resource properties are defined in the Ecore metamodel through annotations. For example, the inputPort property of a Simulink block has a generalization relationship with the port property of an MBSE block as shown below (line 27 of simulink4MBSE.ecore).
```text
<eStructuralFeatures xsi:type="ecore:EReference" name="inputPort" upperBound="-1"
        eType="#//InputPort" containment="true">
      <eAnnotations source="subsets" references="../../org.eclipse.mbse.common.vocabulary/Ecore%20Metamodels/CommonMBSEVocabulary.ecore#//Block/port"/>
    </eStructuralFeatures>
```

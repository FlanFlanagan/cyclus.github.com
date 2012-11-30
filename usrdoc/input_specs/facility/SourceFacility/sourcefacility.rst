
SourceFacility
==============

The SourceFacility module creates material commodities each time step.

Input Parameters
----------------

  * output - information about what this facility outputs
  
    * outcommodity - the output commodity
    * output_capacity - the capacity that can be output each time step
    * `optional` inventorysize - the amount of output commodity that 
      can be stored by the facility
    * recipe - the material recipe (isotopics) that the facility 
      outputs

Definiton
+++++++++

.. code-block:: xml

  <define name="SourceFacility">
     <element name="SourceFacility"> 
       <element name ="output">
         <ref name="outcommodity"/>
         <ref name="output_capacity"/>
         <optional>
           <ref name="inventorysize"/>
         </optional>
         <element name="recipe">
           <data type="string"/>
         </element>
       </element>
     </element>
  </define>

Example
+++++++

.. code-block:: xml

  <facility>
    <name>Source</name>
    <lifetime>5</lifetime>
    <model>
      <SourceFacility>
	<output>
	  <outcommodity>fuel</outcommodity>     <!-- this facility outputs fuel -->
	  <output_capacity>1</output_capacity>  <!-- at 1 kg per time step -->
	  <recipe>fuel_recipe</recipe>          <!-- with the isotopics described by the fuel_recipe -->
	</output>
      </SourceFacility>
    </model>
    <outcommodity>fuel</outcommodity>
  </facility>


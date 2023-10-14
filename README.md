## EECS_4412_A2
  - A simple Decision tree program
  - Part 1: creating a function to determine if a node is an Internal or a Leaf node
  - Part 2: Creating a function that calculates the entropy (Measure of Impurity in the data) of a node to be used for splitting a node based on the Information Gain criterion
  - Part 3: Use the entropy function to calculate the Information Gain of a node to determine which attribute is the best attribute to split on
  - Part 4: Use the functions created in Part 2 & 3 to determine the best attribute that has the highest Information Gain so that the values (examples) in the node can be split on that attribute
  - Part 5: Splitting the nodes at each level by using the above functions using the information gaain criteria.
      - What the function does:
        ![2](https://github.com/nadim365/EECS_4412_A2/assets/26136606/50114717-4480-4708-8017-4b758bcaa02b)

      - Structure of the variables:
          - The dataframe of the previous level that we will create the children from:
             ```python
              dataframe_dict = {"Node_1_1": the dataframe at the root node}
            ```
          - after first pass:
             ```python
                dataframe_dict = {
                 "Node_2_1": dataframe_2_1,
                 "Node_2_2": dataframe_2_2,
                 "Node_2_3": dataframe_2_3
             }
              ```
          - Attributes remaining after splitting the nodes at each level:
            - ```python
              remaining_attrs = {"Node_1_1": ["BUYING", "MAINTENANCE", "DOORS", "PERSONS", "LUG_BOOT", "SAFETY"]}
              ```
            - after first pass (assuming we're splitting on attr "PERSONS"):
            - ```python
                remaining attrs = {
                  "Node_2_1": ["BUYING", "MAINTENANCE", "DOORS", "LUG_BOOT", "SAFETY"],
                 "Node_2_2": ["BUYING", "MAINTENANCE", "DOORS", "LUG_BOOT", "SAFETY"],
                 "Node_2_3": ["BUYING", "MAINTENANCE", "DOORS", "LUG_BOOT", "SAFETY"]
              }
            ```
          - The tree model which contains information about the current state of the tree:
            -  ```python
               tree_model = [tree_connectivity, node_types, node_labels]
               ```
           - visual rep. of what will be store in the tree_model:
             ![3](https://github.com/nadim365/EECS_4412_A2/assets/26136606/bbf90c98-1223-4076-b6d0-8b3cc866e540)
           - After first pass:
             ![4](https://github.com/nadim365/EECS_4412_A2/assets/26136606/a417f65a-0b0f-4555-957d-6658050d12e8)

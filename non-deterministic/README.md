# NonDeterministic Datasets

Datasets used for the experiments in **ECAI 2023** to test Plan4Past in the _nondeterministic_ setting.

## Structure

- `LTLf/`
    - `C17/` contains the original set of instances from [Camacho et al., 2017]
    - `BF23/` contains the newly generated instances with temporally extended goals in LTLf [Bonassi et al., 2023, ECAI]

- `PPLTL/`
    - `C17/` contains the set of instances from [Camacho et al., 2017] with Temporally Extended Goals translated in PPLTL by us
    - `BF23/` contains the newly generated instances with Temporally Extended Goals formulated in PPLTL

Such folders are furter partitioned in other subfolders, one for each domain. 
For every domain we provide all the PDDL files and a "tegs.json" file containing all temporally extended goals employed for the domain.
tegs.json contains a dictionary where:

- The `key` is the name of a PDDL instance
- The `value` is the temporal goal corresponding to the `key` instance
    
### Examples

#### Example 1: rovers with PPLTL goals of type 1 (ROVERS-1 in the paper)

Rovers with PPLTL goals of type (1) is under the folder `non-deterministic/PPLTL/23/rovers_1/`, which contains the PDDL files and "tegs.json".
In "tegs.json", the entry:

`"p01": "O(communicatedsoildata_waypoint2) & O(communicatedrockdata_waypoint3) & O(communicatedimagedata_objective1_highres)"`

indicates that the temporal goal of p01 is "O(communicatedsoildata_waypoint2) & O(communicatedrockdata_waypoint3) & O(communicatedimagedata_objective1_highres)".

#### Example 2: robot-coffee with LTLf goals of type 4 (COFFEE-4 in the paper)

Robot-coffee with LTLf goals of type (4) is under the folder `non-deterministic/LTLf/BF23/robot_4/`, which contains the PDDL files and "tegs.json".
In "tegs.json", the entry:

`"new_coffee2": "X(X(X(X(X(X(X((robot_at c))))))))"`

indicates that the temporal goal of instance new_coffee2 is "X(X(X(X(X(X(X((robot_at c))))))))".

#### Example 3: blocksworld instances by [Camacho et al., 2017] with goals translated in PPLTL by us (BLOCKS in the paper)

The instances of blocksworld by [Camacho et al., 2017] with the goals we translated in PPLTL are under the folder `PPLTL/C17/blocksworld/`, which contains the PDDL files and "tegs.json".
In "tegs.json", the entry:

`"a03": "(O(on_d_table)) S (O(on_a_table) & O(on_b_table) & O(on_c_table))"`

indicates that the temporal goal of instance a03 is "(O(on_d_table)) S (O(on_a_table) & O(on_b_table) & O(on_c_table))".


## References

- [Bonassi et al., 2023, ECAI]: Bonassi, De Giacomo, Favorito, Fuggitti, Gerevini, and Scala. FOND Planning for 
Pure-Past Linear Temporal Logic Goals. ECAI 2023.
- [Camacho et al., 2017]: Camacho, Triantafillou, Muise, Baier, and McIlraith. Non-Deterministic Planning with 
Temporally Extended Goals: LTL over Finite and Infinite Traces. AAAI 2017.
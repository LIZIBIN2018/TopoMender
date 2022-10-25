TopoMender Software
Qian-Yi Zhou (qianyizh@stanford.edu)
Version : 1.04, last updated on 8/14/2013


I. Introduction

TopoMender is a software aiming for volume data topology repair, based on paper 'Topology Repair of Solid Models Using Skeletons' submitted to Trans. Vis. Comput. Graph.(visit my homepage 'http://cg.cs.tsinghua.edu.cn/people/~zqy/' to get a copy.) 

This program reads a volume data file (stored in SOG format, which could be generated from PolyMender software 'http://www.cs.wustl.edu/~taoju/code/polymender.htm'), break or fill the handles under a given size, and then generate a polygonal mesh stored in PLY or OBJ format. This program is both robust and efficient, as it never introduce invalid geometry or additional handles, and consumes a small amount of time and memory space. 


II. Usage & Models

Usage :   TopoMender [-skt] SOGFile ThinThresh GrowThresh ModelFile
Example : TopoMender eight.sog 1.0 1.0 eight.ply

SOGFile :    Input file, must be of SOG file format
ModelFile :  Output file, could be of either OBJ or PLY file format
ThinThresh : A threshold used in thinning process, if it is less or equal than 0.0, no breaking operation is done
GrowThresh : A threshold used in growing process, if it is less or equal than 0.0, no filling operation is done
-skt :       Indicates a corresponding SKT file (skeleton file) would be generated

Three test models are included in the model package, they are:

a) bad_spiderweb model (provided by Cindy Grimm) - a messed up spiderweb.
Recommended command:
> PolyMender-qd-clean bad_spiderweb.ply 7 0.99 bad_spiderweb.7.sog
> TopoMender bad_spiderweb.7.sog 0.0 1.0 bad_spiderweb.7.ply

b) fix_knotty (provided by Cindy Grimm) - a knotty and a dual knotty
Recommended command:
> PolyMender-qd-clean fix_knotty.ply 8 0.9 fix_knotty.8.sog
> TopoMender fix_knotty.8.sog 1.0 1.0 fix_knotty.8.ply

c) wisky (provided by Tao Ju) - a blocked handle
Recommended command:
> PolyMender-qd-clean wisky.ply 5 0.9 wisky.5.sog
> TopoMender wisky.5.sog 1.0 0.0 wisky.5.ply


III. Release Notes :

Version 1.0 (Oct. 14, 2006) :
A first console executable file, containing all the basic functions.


IV. Acknowledgement

I would like to thank Tao Ju for the idea discussion, his PolyMender software and Wisky model. 
I would also like to thank Cindy Grimm for providing the Knotty and Spiderweb models.
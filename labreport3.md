# Lab Report 3
## part 1
## Failure inducing inputs
```
@Test 
	public void testReverseInPlace() {
    int[] input1 = { 1,2,3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3,2,1 }, input1);
	}
```
## Input that doesnt cause failure 
```
@Test 
	public void testReverseInPlace() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
	}
```
## Symptom
![Image](https://github.com/ishi1022/cse15l-lab-reports/blob/main/Screen%20Shot%202024-02-12%20at%205.23.07%20PM.png?raw=true)
## Code before fixing the bug
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
```
## Code after fixing the bug
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length/2; i += 1) {
      int temp = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - i - 1] = temp;
    }
  }
```
This fix makes sure that it only goes till the midpoint of the array and swaps the elements till there as only that is necessary becasue by this halfway point all the elements would be swapped.

## part 2
## Command line options for ```find```
## 1: Finding files with multiple combinations with logical operators:
- ```'-a'``` (AND), ```'-o'``` (OR), ```'!'``` (NOT)
- (ex) ```find /path/to/search -name "*.txt" - o -name "*.pdf``` allows you to combine multiple search conditions using logical operators. 

## 2: Finding Files by Type:
- ```'-type'```
- (ex) ```find /path/to/search -type f``` allows you to search for files by a specific type.

## 3: Finding Directories with Type:
- ```'-type d'```
- (ex) ```find /path/to/search -type d``` allows you to search for directories.

## 4: Finding files by Size 
- ```'-size'```
- (ex) ```find /path/to/search -type f -size +1M``` ,allows you to search for files based on their size. 

## Commands on ```./technical``` file
1. ```-o``` this searches for the files in the fiction/eggan directory that have either a .txt file extension or a .anc file extension. This is useful when wanting to find files that match one of many criterias.
```
ishifishi@Ishvaris-MacBook-Pro eggan % find /Users/ishifishi/Downloads/OANC-GrAF/data/written_1/fiction/eggan -name "*.txt" -o -name "*.anc"
/Users/ishifishi/Downloads/OANC-GrAF/data/written_1/fiction/eggan/TheStory.txt
/Users/ishifishi/Downloads/OANC-GrAF/data/written_1/fiction/eggan/TheStory.anc
```
```!``` this Not operator seaches for files in this directory that dont have the .txt file extension. This is useful when wanting to fin dall files other than certain ones. 
```
ishifishi@Ishvaris-MBP OANC-GrAF % find /Users/ishifishi/Downloads/OANC-GrAF/data/written_1/fiction/eggan ! -name "*.txt" 
/Users/ishifishi/Downloads/OANC-GrAF/data/written_1/fiction/eggan
/Users/ishifishi/Downloads/OANC-GrAF/data/written_1/fiction/eggan/TheStory-s.xml
/Users/ishifishi/Downloads/OANC-GrAF/data/written_1/fiction/eggan/TheStory-logical.xml
/Users/ishifishi/Downloads/OANC-GrAF/data/written_1/fiction/eggan/TheStory-np.xml
/Users/ishifishi/Downloads/OANC-GrAF/data/written_1/fiction/eggan/TheStory-vp.xml
/Users/ishifishi/Downloads/OANC-GrAF/data/written_1/fiction/eggan/TheStory.anc
/Users/ishifishi/Downloads/OANC-GrAF/data/written_1/fiction/eggan/TheStory-hepple.xml
```
2. ```-type f``` this option searched for regular files in the directory, the f specifies the search to only files. This is useful wehn you want to find files within a directory.
```
ishifishi@Ishvaris-MBP OANC-GrAF % find /Users/ishifishi/Downloads/OANC-GrAF/data/written_1/fiction/eggan -type f 
/Users/ishifishi/Downloads/OANC-GrAF/data/written_1/fiction/eggan/TheStory.txt
/Users/ishifishi/Downloads/OANC-GrAF/data/written_1/fiction/eggan/TheStory-s.xml
/Users/ishifishi/Downloads/OANC-GrAF/data/written_1/fiction/eggan/TheStory-logical.xml
/Users/ishifishi/Downloads/OANC-GrAF/data/written_1/fiction/eggan/TheStory-np.xml
/Users/ishifishi/Downloads/OANC-GrAF/data/written_1/fiction/eggan/TheStory-vp.xml
/Users/ishifishi/Downloads/OANC-GrAF/data/written_1/fiction/eggan/TheStory.anc
/Users/ishifishi/Downloads/OANC-GrAF/data/written_1/fiction/eggan/TheStory-hepple.xml
```
```
ishifishi@Ishvaris-MBP OANC-GrAF % find /Users/ishifishi/Downloads/OANC-GrAF/data/written_2/non-f
iction/OUP/Berk -type f
/Users/ishifishi/Downloads/OANC-GrAF/data/written_2/non-fiction/OUP/Berk/CH4-s.xml
/Users/ishifishi/Downloads/OANC-GrAF/data/written_2/non-fiction/OUP/Berk/ch2-np.xml
/Users/ishifishi/Downloads/OANC-GrAF/data/written_2/non-fiction/OUP/Berk/ch2-s.xml
/Users/ishifishi/Downloads/OANC-GrAF/data/written_2/non-fiction/OUP/Berk/ch2-vp.xml
/Users/ishifishi/Downloads/OANC-GrAF/data/written_2/non-fiction/OUP/Berk/ch2.txt
/Users/ishifishi/Downloads/OANC-GrAF/data/written_2/non-fiction/OUP/Berk/ch7-s.xml
/Users/ishifishi/Downloads/OANC-GrAF/data/written_2/non-fiction/OUP/Berk/CH4-np.xml
/Users/ishifishi/Downloads/OANC-GrAF/data/written_2/non-fiction/OUP/Berk/ch1.txt
/Users/ishifishi/Downloads/OANC-GrAF/data/written_2/non-fiction/OUP/Berk/CH4.txt
/Users/ishifishi/Downloads/OANC-GrAF/data/written_2/non-fiction/OUP/Berk/ch1-s.xml
/Users/ishifishi/Downloads/OANC-GrAF/data/written_2/non-fiction/OUP/Berk/CH4-vp.xml
/Users/ishifishi/Downloads/OANC-GrAF/data/written_2/non-fiction/OUP/Berk/ch7.txt
/Users/ishifishi/Downloads/OANC-GrAF/data/written_2/non-fiction/OUP/Berk/ch2-logical.xml
/Users/ishifishi/Downloads/OANC-GrAF/data/written_2/non-fiction/OUP/Berk/ch1-vp.xml
/Users/ishifishi/Downloads/OANC-GrAF/data/written_2/non-fiction/OUP/Berk/ch7-logical.xml
/Users/ishifishi/Downloads/OANC-GrAF/data/written_2/non-fiction/OUP/Berk/ch1-np.xml
/Users/ishifishi/Downloads/OANC-GrAF/data/written_2/non-fiction/OUP/Berk/ch7-vp.xml
/Users/ishifishi/Downloads/OANC-GrAF/data/written_2/non-fiction/OUP/Berk/CH4.anc
/Users/ishifishi/Downloads/OANC-GrAF/data/written_2/non-fiction/OUP/Berk/CH4-logical.xml
/Users/ishifishi/Downloads/OANC-GrAF/data/written_2/non-fiction/OUP/Berk/ch7.anc
/Users/ishifishi/Downloads/OANC-GrAF/data/written_2/non-fiction/OUP/Berk/ch7-np.xml
/Users/ishifishi/Downloads/OANC-GrAF/data/written_2/non-fiction/OUP/Berk/ch2.anc
/Users/ishifishi/Downloads/OANC-GrAF/data/written_2/non-fiction/OUP/Berk/ch1.anc
/Users/ishifishi/Downloads/OANC-GrAF/data/written_2/non-fiction/OUP/Berk/ch1-logical.xml
```
 3. ```-type d``` this searches for directories in the non-fiction directory. It is useful when wanting to locate directories within a directory structure.
```
ishifishi@Ishvaris-MBP OANC-GrAF % find /Users/ishifishi/Downloads/OANC-GrAF/data/written_2/non-fiction  -type d        
/Users/ishifishi/Downloads/OANC-GrAF/data/written_2/non-fiction
/Users/ishifishi/Downloads/OANC-GrAF/data/written_2/non-fiction/OUP
/Users/ishifishi/Downloads/OANC-GrAF/data/written_2/non-fiction/OUP/Berk
/Users/ishifishi/Downloads/OANC-GrAF/data/written_2/non-fiction/OUP/Abernathy
/Users/ishifishi/Downloads/OANC-GrAF/data/written_2/non-fiction/OUP/Rybczynski
/Users/ishifishi/Downloads/OANC-GrAF/data/written_2/non-fiction/OUP/Kauffman
/Users/ishifishi/Downloads/OANC-GrAF/data/written_2/non-fiction/OUP/Fletcher
/Users/ishifishi/Downloads/OANC-GrAF/data/written_2/non-fiction/OUP/Castro
```
```
ishifishi@Ishvaris-MBP OANC-GrAF % find /Users/ishifishi/Downloads/OANC-GrAF/data/spoken -type d
/Users/ishifishi/Downloads/OANC-GrAF/data/spoken
/Users/ishifishi/Downloads/OANC-GrAF/data/spoken/face-to-face
/Users/ishifishi/Downloads/OANC-GrAF/data/spoken/face-to-face/charlotte
/Users/ishifishi/Downloads/OANC-GrAF/data/spoken/telephone
/Users/ishifishi/Downloads/OANC-GrAF/data/spoken/telephone/switchboard
/Users/ishifishi/Downloads/OANC-GrAF/data/spoken/telephone/switchboard/32
/Users/ishifishi/Downloads/OANC-GrAF/data/spoken/telephone/switchboard/35
/Users/ishifishi/Downloads/OANC-GrAF/data/spoken/telephone/switchboard/34
/Users/ishifishi/Downloads/OANC-GrAF/data/spoken/telephone/switchboard/33
/Users/ishifishi/Downloads/OANC-GrAF/data/spoken/telephone/switchboard/20
/Users/ishifishi/Downloads/OANC-GrAF/data/spoken/telephone/switchboard/27
/Users/ishifishi/Downloads/OANC-GrAF/data/spoken/telephone/switchboard/29
/Users/ishifishi/Downloads/OANC-GrAF/data/spoken/telephone/switchboard/42
/Users/ishifishi/Downloads/OANC-GrAF/data/spoken/telephone/switchboard/45
/Users/ishifishi/Downloads/OANC-GrAF/data/spoken/telephone/switchboard/28
/Users/ishifishi/Downloads/OANC-GrAF/data/spoken/telephone/switchboard/26
/Users/ishifishi/Downloads/OANC-GrAF/data/spoken/telephone/switchboard/21
/Users/ishifishi/Downloads/OANC-GrAF/data/spoken/telephone/switchboard/44
/Users/ishifishi/Downloads/OANC-GrAF/data/spoken/telephone/switchboard/43
/Users/ishifishi/Downloads/OANC-GrAF/data/spoken/telephone/switchboard/38
/Users/ishifishi/Downloads/OANC-GrAF/data/spoken/telephone/switchboard/36
/Users/ishifishi/Downloads/OANC-GrAF/data/spoken/telephone/switchboard/31
/Users/ishifishi/Downloads/OANC-GrAF/data/spoken/telephone/switchboard/30
/Users/ishifishi/Downloads/OANC-GrAF/data/spoken/telephone/switchboard/37
/Users/ishifishi/Downloads/OANC-GrAF/data/spoken/telephone/switchboard/39
/Users/ishifishi/Downloads/OANC-GrAF/data/spoken/telephone/switchboard/46
/Users/ishifishi/Downloads/OANC-GrAF/data/spoken/telephone/switchboard/41
/Users/ishifishi/Downloads/OANC-GrAF/data/spoken/telephone/switchboard/48
/Users/ishifishi/Downloads/OANC-GrAF/data/spoken/telephone/switchboard/24
/Users/ishifishi/Downloads/OANC-GrAF/data/spoken/telephone/switchboard/23
/Users/ishifishi/Downloads/OANC-GrAF/data/spoken/telephone/switchboard/49
/Users/ishifishi/Downloads/OANC-GrAF/data/spoken/telephone/switchboard/40
/Users/ishifishi/Downloads/OANC-GrAF/data/spoken/telephone/switchboard/47
/Users/ishifishi/Downloads/OANC-GrAF/data/spoken/telephone/switchboard/22
/Users/ishifishi/Downloads/OANC-GrAF/data/spoken/telephone/switchboard/2
```
4.```-size``` the +1000 seachea for files wihtin the directory that are larger than 1000 bytes. It is useful when you want to find files that are not exceeding a sertain size. The +10000 searches for files larger then 10000 bytes. You can also use this function with a - ign to find files smaller than a certain size. 
```
ishifishi@Ishvaris-MBP OANC-GrAF % find /Users/ishifishi/Downloads/OANC-GrAF/data/written_1/fiction/eggan -type f -size +1000
/Users/ishifishi/Downloads/OANC-GrAF/data/written_1/fiction/eggan/TheStory-s.xml
/Users/ishifishi/Downloads/OANC-GrAF/data/written_1/fiction/eggan/TheStory-logical.xml
/Users/ishifishi/Downloads/OANC-GrAF/data/written_1/fiction/eggan/TheStory-np.xml
/Users/ishifishi/Downloads/OANC-GrAF/data/written_1/fiction/eggan/TheStory-vp.xml
/Users/ishifishi/Downloads/OANC-GrAF/data/written_1/fiction/eggan/TheStory-hepple.xml

```
```
ishifishi@Ishvaris-MBP OANC-GrAF % find /Users/ishifishi/Downloads/OANC-GrAF/data/written_1/fiction/eggan -type f -size +10000
/Users/ishifishi/Downloads/OANC-GrAF/data/written_1/fiction/eggan/TheStory-hepple.xml
```
**I used this website to find the command line options https://snapshooter.com/learn/linux/find it provided me with details on each command line arguemtent and how to use each.**

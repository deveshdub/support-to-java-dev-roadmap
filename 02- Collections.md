Collection:
group of individual obj that ar represented as group called collection.
two main interfaces: java.uti.Collection & java.util.map.

Class: user defined blueprint or prototype from which obj are created.
it define set of properties or method that are common to all obj of one type.

Interface: Like a class, inteface can have method & variable but methods are not defined in it.
only method signature, no body. interface declare what a class should do not how. its blueprint of class.

METHODS of collection interace. {Collection obj.method()}
add(Object), addAll(Collection c, T... elements) three dots means denote varrags(allow method to have zero or more arg of specific type), compiler treat is as array
clear(), contains(object o); containsAll(Collection<?> obj), equals()-> {shallow & Deep Caomparison}; hashcode().
The equals() and hashCode() methods in Java are related by a contract: if two objects are considered equal according to equals(), 
they must have the same hashCode(). This ensures that collections like HashSet and HashMap work correctly when comparing objects. In essence, equals() determines if two objects are logically the same, while hashCode() provides a numerical representation that helps with efficient storage and retrieval in hash-based collections. 
isEmpty(),
iterator():java.util.iterator;	Iteratot<E> itr=collection.iterator();uni direcetion:- forward direction; interface used to traverse elements in collection sequentially. proides methods like hasNext(),next() & remove.
ListIterator: ListIterator<E> listItr= list.listIterator(); both forward and backward traverse allow removal and modification too of element.
Enumeration: Enumeration<E> e= collection.elements(); older interface from java 1.0 only forward iteration, not allow removal.
Java Sequential Streams: process element in sequential manner, one at a time.
Java Parallel Stream: to use multiple core of processor. order of execution will be random so use where order wont matter.
remove(Object o) or remove(int index);
boolean removeAll(Collection<?> c);
removeIf(Predicate filter): boolean removeIf(Predicate<? super E> filter); eg. list.removeIf(n->n%2 !=0);
retainAll (Collection c) returns boolean value. return true if calling collection modified, false if intact.
size(); spliterator():- public Spliterator<E> spliterator(); traverse like iterator but supports parallel programming.
stream(); Stream<T> stream; T is either class, obj, data type;
Stream  isnt data structure, takes input from Collections, Arrays or I/O channels. it dont original changes data structure provide result as pipelined operations.

Diffrent operations in Streams: (1)Intermediate Operations (2)Terminal Operations.
Intermediate operation: benefit: no storage,laziness, pipelined of functions,can be infinite, can be parallelized, can be created from collection, arrays, File lines,Method in stream.
map(): <R> Stream<R> map(Function<? super T,? extends R> mapper) {A functional interface that takes a T and returns an R. This is what map() applies to every element of the stream.}
2. filter(): Stream<T>filter(Predicate<?super T>predicate)
3. sorted(): Stream<T> sorted();
		Stream<T> sorted(Comparator<?super T> comparator)
4 flatmap: this operation in java stream is used to flatter stream of collection into stream of element.
5. distinct(): Stream<T> distinct(); remove distinct element.
6 peek(): perform action w/o modifying this stream. returns a stream consiting value of this stream in addition with other.

method refrence: its a shorthand syntax for writing a lambda expression that simply calls a method. eg. list.forEach(s->System.out.println(s)); we use list.forEach(System.out::println);
🔹 Types of Method References
Type		Syntax				Example
Static method	ClassName::staticMethodName	Integer::parseInt
Instance method object::instanceMethodName	System.out::println
of object
Instance method ClassName::instanceMethodName	String::toLowerCase
of type
Constructor 	ClassName::new			ArrayList::new
reference	

🔹 Transforming Lambda to Method Reference
Lambda Expression			Method Reference Equivalent
x -> x.toLowerCase()			String::toLowerCase
x -> System.out.println(x)		System.out::println
x -> new ArrayList<>()			ArrayList::new
(x, y) -> x.compareToIgnoreCase(y)	String::compareToIgnoreCase
✅ Use it when:
You’re just calling a method inside the lambda.
It improves readability and removes redundancy.
🚫 Avoid it when:
You need custom logic inside the lambda.
You’re performing multiple steps (not just calling one method).

Terminal Operations: Operations that returns a result.
1) Collect(): it is used to return the result of intermediate method.syntax.  <R,A> R Collect(Collector<? super T,A,R> collector) T is  type of element in stream(String) A= the obj that accumulated stream element (like streambuilder or list eg List<String>) R= final collected result.
2) forEach(): this method to iterate througu every element of steram. void forEach(consumer<?super T>action) : MEANING: its a cosumer function interface( which takes one input and return nothing) of type T or super class of T
3) reduce(): reduce element of stream to value. T reduce (T identity, BinaryOperator<T> accumulator) eg: int sum = numbers.stream().reduce(0, (a, b) -> a + b); // identity = 0 OR String result = words.stream().reduce("", (a, b) -> a + "-" + b);
4)count(): return count of element in stream: Syntax:- long count();
5) findFirst(): Return the first element of stream if present. Syntax: Optional<T> findFIrst();
6) allMatch(): check if stream element match predicate.syntax:- boolean allMatch(Predicate<? super T> predicate)
7)anyMatch(): check if any match. syntax:-  boolean anyMatch(Predicate<?Super T> predicate).

Interface that extends java collection interface.
1. Iterable interface.
2. Collection Interface.
3. List Interace. List <T> al = new ArrayList<> (); List <T> ll = new LinkedList<> (); List <T> v = new Vector<> (); ArrayList can not be used for primitive types, like int, char, etc. We will need a wrapper class(Integer, Character) for such cases. 
4. Stack: last in- first out: pop push method, empty, search, peek operations.
5. Queue Interface.:Queue <T> pq = new PriorityQueue<> (); Queue <T> ad = new ArrayDeque<> (); Dequeue: double ended queue
	ArrayDeque implements it. addFirst(), addLast() methods.
6. Set Interface. Set<T> hs = new HashSet<> (); Set<T> lhs = new LinkedHashSet<> (); Set<T> ts = new TreeSet<> (); 
set is a unordered collection of object, in which duplicate values cant enter.
7. SortedSet: Treeset
8. Map Interface.Map<T> hm = new HashMap<> (); Map<T> tm = new TreeMap<> ();
Map is data structure that supports ket value pair for mapping data, no duplicate key, but duplicate value under two diff key.
Hashmap uses hashing, which convert the large String into small String that represent same string just to make operation faster.


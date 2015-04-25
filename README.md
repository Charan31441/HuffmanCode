#					***My Algorithm For Huffman Coding***
1.First i created a double linked list in which it stores the address of next node and address of down root(which  contains adress of left child and right child).

2.Now I have performed sorted insertion in to linked list and made down root adresses of left and right childs as NULL.

3.To get more clarity,In the folder I have attached the figure of list which I used linkedlist.jpg

4.Now I am creating a new node with data as firstnode->data + second->node->data and giving firstnode as right adress and secondnode as left address.

5.Deleting firstnode and second node and performing sorted insertion of new node in to the linked list.

6.I will continue this process untill list has only one node(head).

7.tree=head->down;Now Huffman tree was formed.

8.Now am travelling rightside from root to leaves ,then am deleting that leaf,I will travel left side if rightnode is null and left node exists,while travelling right am storing 1 and while travelling left am storing 0 in an array.


encoding(root,arr,top)

begin

	if (tree->left)

	{

		arr[top] = 0;

		encoding(tree->left, arr, top + 1);

	}

	if (tree->right)

	{

		arr[top] = 1;

		encoding(tree->right, arr, top + 1);

	}

	if (isLeaf(tree))

	{

		int a,b;

		a=tree->data;

		int p;

		int j;

		int sum=0;

		for(j=0;j<top;j++)

		{

			sum=sum+(arr[j]*(pow(10,(top-j-1))));

		}

		b=sum;

		insert_code(a,b);/*which inserts in new linked list (huffman_code)which consists of data(a),code(b),and address of next node*/ 
	}

end

9.Now again am reading integers from an input file and am searching that integer in new linked list i:e;huffman_code and the code in that node  in to Output file.

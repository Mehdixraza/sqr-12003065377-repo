# sqr-12003065377-repo
class Node:
    def __init__(self, data=None, left=None, right=None):
        self.left = left
        self.right = right
        self.data = data

class BTree:
    def __init__(self, root):
        self.root = root

    def CreateTree(self, root):
        self.root.data = raw_input("Enter data,'*' means empty: ")
        if self.root.data == '*':
            return
        self.root.left = Node()
        self.root.right = Node()
        self.CreateTree(self.root.left)
        self.CreateTree(self.root.right)

    def PreOrder(self):
    if self.root != None:
        if self.root.data != '*':
            print self.root.data,
            self.root.left.PreOrder()
            self.root.right.PreOrder()

if __name__ == '__main__':
    t = Node()
    bt = BTree(t)
    bt.CreateTree(t)
    bt.PreOrder(t)

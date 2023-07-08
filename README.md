# assign-5
# XML 1 - Find the Score
import sys
import xml.etree.ElementTree as etree

def get_attr_number(node):
    # your code goes here
    # XML 1 - Find the Score in Python - Hacker Rank Solution START
    count = 0
    for tag in node:
        count = count + get_attr_number(tag)
    return count + len(node.attrib)
    # XML 1 - Find the Score in Python - Hacker Rank Solution END

if __name__ == '__main__':
    sys.stdin.readline()
    xml = sys.stdin.read()
    tree = etree.ElementTree(etree.fromstring(xml))
    root = tree.getroot()
    print(get_attr_number(root))

    # XML2 - Find the Maximum Depth

    
    import xml.etree.ElementTree as etree

maxdepth = 0
def depth(elem, level):
    global maxdepth
    # your code goes here
    # XML2 - Find the Maximum Depth in Python - Hacker Rank Solution START
    if (level == maxdepth):
        maxdepth += 1
    for child in elem:
        depth(child, level + 1)
    # XML2 - Find the Maximum Depth in Python - Hacker Rank Solution END

if __name__ == '__main__':
    n = int(input())
    xml = ""
    for i in range(n):
        xml =  xml + input() + "\n"
    tree = etree.ElementTree(etree.fromstring(xml))
    depth(tree.getroot(), -1)
    print(maxdepth)

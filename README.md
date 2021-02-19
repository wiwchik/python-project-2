    # Global constants indicating indices in the linked list node
    VALUE = 0
    NEXT = 1
    PREV = 2


    # Linear doubly linked list with head and tail
    def add_to_back_4(value, head, tail):
        item = [value, None, None]
        if head is None:
            head = item
        else:
            tail[NEXT] = item
            item[PREV] = tail
        tail = item
        return head, tail


    def add_to_front_4(value, head, tail):
        item = [value, None, None]
        if tail is None:
            tail = item
        else:
            head[PREV] = item
            item[NEXT] = head
        head = item
        return head, tail


    def print_el(head, tail):
        while head != tail:
            print(head)
            head = head[NEXT]
        print(tail)


    def get_el_by_index(n, head, tail):
        k = 0
        head1 = head
        while head1 != tail:
            k = k + 1
            head1 = head1[NEXT]
        for i in range(k + 1):
            if n == i:
                return head
            if i != k + 1:
                head = head[NEXT]
            else:
                head = tail


    def remove_last_el(tail):
       tail = tail[PREV]
       return tail


    def remove_first_el(head):
        head = head[NEXT]
        return head


    def search_by_value(v, head, tail):
        k = 0
        head1 = head
        while head1 != tail:
            k = k + 1
            head1 = head1[NEXT]
        for i in range(k + 1):
            if head[0] == v:
                print(head)
            head = head[NEXT]


    '''
    # At the beginning, the linked list is empty, head and tail point nowhere
    head = tail = None

    # Start adding new elements
    head, tail = add_to_back_4(10, head, tail)
    head, tail = add_to_back_4(20, head, tail)
    head, tail = add_to_back_4(30, head, tail)
    head, tail = add_to_back_4(40, head, tail)
    head, tail = add_to_front_4(10, head, tail)
    head, tail = add_to_front_4(20, head, tail)
    print_el(head, tail)
    print(get_el_by_index(4, head, tail))
    search_by_value(10, head, tail)
    tail = remove_last_el(tail)
    head = remove_first_el(head)
    '''

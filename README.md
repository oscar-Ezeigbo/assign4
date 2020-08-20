# assign4

the code is a c++ code for Dijkstras shortest path algorith but unfortunately i was unable to make it in such a way that the vertices can be created in any external means without complicating the code to the point where i dont understand it. so this will just be how to edit the vertices and edges 

int main()
{
    Graph g;
    g.add_vertex('A', { {'B', 3}, {'C', 1} }); // making the verteces is quite simple, just input the name of the next vertex and its edge number. you can have an unequal number of edges vs actual number verteces that will be used, i.e giving 'A' up to 10 edges even if you only use 6 verteces. because the verteces are dynamically inputed there is no way to write the code in such a way that it limits this while leaving room for user input. this also has the effect of making the codes accuracy based entirely off the users input. 
    g.add_vertex('B', { {'A', 3}, {'E', 2}, {'D', 1} });
    g.add_vertex('C', { {'A', 1}, {'E', 5}, {'F', 6} });
    g.add_vertex('D', { {'F', 2}, {'E', 3}, {'B', 1} });
    g.add_vertex('E', { {'C', 5}, {'B', 2}, {'D', 3}, {'F', 1} });
    g.add_vertex('F', { {'C', 6}, {'E', 1}, {'D', 2} });
   

    for (char vertex : g.shortest_path('A', 'E'))// just input the vertex you want to start from and the one you want to get to. 
    {
        cout << vertex << endl;
    }

it is possible to get the correct answer even with differnt inputs in a way because the code only reads from the connecting vertex. it also presumes that it is possible to get from the start to the end point, meaning that if the connecting vertex leads to a dead end it will show a blank screen. it is also capable of backtracking because the results are only printed once a route is found meaning if there is a feasable way to get there, it should be able to. 

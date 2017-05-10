# Quicksort-with-POSIX-Thread

### Using the code
```
void *thread_quicksort(void *arg)
{   qs_param *qp;
    qp = (qs_param *) arg;
    int a = qp->a;
    int l = qp->l;
    int r = qp->r;
    int p = qp->p;
    int j;
    if( l < r ) 
    {
        j = partition(a, l, r);
        qs_param *qp_left;
        qp_left->a = a;
        qp_left->l = l;
        qp_left->r = j - 1
        qp_left->p = p - 1
        qs_param *qp_right;
        qp_right->a = a;
        qp_right->l = j + 1;
        qp_right->r = r;
        qp_right->p = p - 1;
        if(p > 0)
        {
            pthread_create(&thread[2*(p - 1)], NULL, 
                thread_quicksort, (void*)%qp_left);
            pthread_create(&thread[2*(p - 1) + 1], NULL, 
                thread_quicksort, (void*)%qp_left);
        }
        else
        {
            quicksort(a, l, j - 1, 0);
            quicksort(a, j + 1, r, 0);
        }
    }

}
```

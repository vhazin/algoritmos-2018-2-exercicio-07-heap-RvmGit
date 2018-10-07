#include<stdio.h>
#include <stdlib.h>

typedef struct node{
    int info;
    char name;
    struct node * left;
    struct node * right;
}arvore;

arvore * createTree(char name,int info){
    arvore * root;
    root = malloc(sizeof(arvore));
    root->info = info;
    root->name = name;
    root->left = NULL;
    root->right = NULL;
    return(root);
}

void infixo (arvore * n){
    if (n!=NULL){
        printf("(");
        infixo(n->left);
        printf("%c/%d",n->name,n->info);
        infixo(n->right);
        printf(")");
    }
}

arvore * adicionar(arvore * tree,char name, int prioridade){
    if (tree == 0){
        return(createTree(name,prioridade));
    }else{
        if (prioridade < tree->info){
            tree->left = adicionar(tree->left,name,prioridade);
        }else{
            tree -> right = adicionar(tree->right,name,prioridade);
        }
    }
    return(tree);
}


int main() {
    arvore * tree = NULL;
    int n =1,x,prioridade;
    char rotulo;
    scanf("%d",&n);
    while (n!=0){
        tree = NULL;
        for (x=0;x<n;x++){
            scanf(" %c/%d",&rotulo,&prioridade);
            tree = adicionar(tree,rotulo,prioridade);
        }
        infixo(tree);
        printf("\n");
        scanf("%d",&n);
    }
    
    
    return 0;
}

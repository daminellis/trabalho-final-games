------------------------------------------------------------------------
player movimentaçao basica
------------------------------------------------------------------------
  using UnityEngine;

public class MovimentoBasico : MonoBehaviour
{
    public float velocidade = 5f;

    void Update()
    {
        // Obtém os inputs de movimento horizontal e vertical
        float movimentoHorizontal = Input.GetAxis("Horizontal");
        float movimentoVertical = Input.GetAxis("Vertical");

        // Calcula a direção do movimento
        Vector3 movimento = new Vector3(movimentoHorizontal, movimentoVertical, 0f);

        // Atualiza a posição do objeto com base na direção e velocidade
        transform.position += movimento * velocidade * Time.deltaTime;
    }
}
------------------------------------------------------------------------
Inimigo com movimentação que segue o player
------------------------------------------------------------------------
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Inimigo : MonoBehaviour
{
    private Transform posicaoDoJogador;

    public float velocidadeDoInimigo;

    // Start is called before the first frame update
    void Start()
    {
        posicaoDoJogador = GameObject.FindGameObjectWithTag("Player").transform;
    }

    // Update is called once per frame
    void Update()
    {
        SeguirJogador();
    }

    private void SeguirJogador()
    {
        if (posicaoDoJogador.gameObject != null)
        {
            transform.position = Vector2.MoveTowards(transform.position, posicaoDoJogador.position, velocidadeDoInimigo * Time.deltaTime);
        }
    }
}

------------------------------------------------------------------------
ainda em teste esse, ja possui as animações 
------------------------------------------------------------------------
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class inimigo1_1 : MonoBehaviour
{
    public Animator anim;
    public SpriteRenderer sprite;
    
    private int life = 1;
    public float moveSpeed = 1f;

    public Transform[] pointsToMove;
    public int startingPoint;

    public BoxCollider2D colliderAtk;
    public BoxCollider2D colliderCheckAtk;

    void Start()
    {
        anim = GetComponent<Animator>();
        sprite = GetComponent<SpriteRenderer>();

        transform.position = pointsToMove[startingPoint].transform.position;
    }

    // Update is called once per frame
    void Update()
    {
        if (startingPoint == 0)
        {
            sprite.flipX = true;
            colliderAtk.offset = new Vector2 ( -0.41f, 0.4f);
            colliderCheckAtk.offset = new Vector2 ( -0.41f, 0.4f);
        }
        else
        {
            sprite.flipX =false;
            colliderAtk.offset = new Vector2 (0.41f, 0.4f);
            colliderCheckAtk.offset = new Vector2 (0.41f, 0.4f);
        }

        if (life == 0)
        {
            EnemyDead();
        }
    }

    private void FixedUpdate()
    {
        Move();
    }

    private void Move()
    {
            
        transform.position = Vector2.MoveTowards(transform.position, pointsToMove[startingPoint].transform.position, moveSpeed);
            
        if (SkeletonMeleeCheckAttack == true)
    }
}


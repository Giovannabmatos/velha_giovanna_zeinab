# Jogo da velha: Giovanna e Zeinab
Jogo da velha feito por jovens

## Tecnologias utilizadas
- **HTML**: estrutura do site
- __CSS__: estilização do site
- *_JS_*: funções do site

### Vídeos utilizados para auxiliar a produção do jogo
[Youtube: Jogo da Velha](https://www.youtube.com/watch?v=M258B1b_pMs)

### Alterações feitas no jogo
- Adição do index;
- Adição do JavaScript;
- Adição do CSS;
- Alteração das cores

### Função principal
```
 make_play(position) {
        if (this.gameover || this.board[position] !== '') return false;

        const currentSymbol = this.symbols.options[this.symbols.turn_index];
        this.board[position] = currentSymbol;
        this.draw();

        const winning_sequences_index = this.check_winning_sequences(currentSymbol);
        if (this.is_game_over()){
            this.game_is_over();
        }
        if (winning_sequences_index >= 0) {
            this.game_is_over();
            this.stylize_winner_sequence(this.winning_sequences[winning_sequences_index]);
        } else {
            this.symbols.change();
        }

        return true;
    },

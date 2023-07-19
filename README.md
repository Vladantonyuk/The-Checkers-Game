# The-Checkers-Game
describe('GamesForTheBrain Checkers', () => {
    it('should load the site and make moves', () => {
    // Navigate to the site
    cy.visit('https://www.gamesforthebrain.com/game/checkers/&#39');
    // Confirm the site is up
    cy.url().should('include', '/game/checkers/');
    cy.get('img[name="space42"]').click();
    cy.get('img[name="space33"]').click();
    cy.contains('Make a move').should('exist');
    // waiting for animations
    cy.wait(1000); 
    cy.get('img[name="space33"]').click();
    cy.get('img[name="space24"]').click();
    cy.contains('Make a move').should('exist');
     // waiting for animations
    cy.wait(1000);
    cy.get('img[name="space02"]').click();
     // this should take a blue piece
    cy.get('img[name="space24"]').click();
    cy.contains('Checkers').should('exist');
     // waiting for animations
    cy.wait(1000);
    cy.get('img[name="space22"]').click();
    cy.get('img[name="space33"]').click();
    cy.contains('Checkers').should('exist');
     // waiting for animations
    cy.wait(1000); 
    cy.get('img[name="space51"]').click();
    cy.get('img[name="space42"]').click();
    cy.contains('Checkers').should('exist');
     // waiting for animations
    cy.wait(1000); 
// Restart the game
    cy.get('[href="./"]').click();
    //wait for resrart game 
    cy.wait(1000);
// Confirm that the restarting had been successful
    cy.contains('Select an orange piece to move.').should('exist');
});
 });

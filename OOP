#include <iostream>
using namespace std;

class Hero {
protected:
    string name, type;
    int health, experience;
    double power;

public:
    Hero(string n, string t, int h, double p, int exp) {
        name = n;
        type = t;
        health = h;
        power = p;
        experience = exp;
    }

    void showGameMessage() {
        cout << " Welcome to Fantasy Battle Arena " << endl;
        cout << "Each hero has unique attack and defense abilities.\n" << endl;
    }

    virtual double attack() = 0;
    virtual double defend() = 0;

    virtual void display() {
        cout << "Hero Name: " << name << endl;
        cout << "Hero Type: " << type << endl;
        cout << "Health: " << health << endl;
        cout << "Power: " << power << endl;
        cout << "Experience: " << experience << endl;
    }
};

class Warrior : public Hero {
private:
    string weapon;
    int armor;
    double rage;

public:
    Warrior(string n, int h, double p, int exp, string w, int a, double r)
        : Hero(n, "Warrior", h, p, exp) {
        weapon = w;
        armor = a;
        rage = r;
    }

    double attack() {
        return power * rage + experience * 0.5;
    }

    double defend() {
        return armor * 1.5 + health * 0.2;
    }

    void display() {
        Hero::display();
        cout << "Weapon: " << weapon << endl;
        cout << "Armor: " << armor << endl;
        cout << "Rage Level: " << rage << endl;
    }
};

class Mage : public Hero {
private:
    string spell;
    int mana;
    double multiplier;

public:
    Mage(string n, int h, double p, int exp, string s, int m, double mul)
        : Hero(n, "Mage", h, p, exp) {
        spell = s;
        mana = m;
        multiplier = mul;
    }

    double attack() {
        return power * multiplier + mana * 0.8;
    }

    double defend() {
        return mana * 0.5 + health * 0.3;
    }

    void display() {
        Hero::display();
        cout << "Spell: " << spell << endl;
        cout << "Mana: " << mana << endl;
        cout << "Magic Multiplier: " << multiplier << endl;
    }
}; // ? FIXED: closing Mage class

class Archer : public Hero {
private:
    string bow;
    int arrows;
    double accuracy;

public:
    Archer(string n, int h, double p, int exp, string b, int ar, double acc)
        : Hero(n, "Archer", h, p, exp) {
        bow = b;
        arrows = ar;
        accuracy = acc;
    }

    double attack() {
        return power * accuracy + arrows * 0.3;
    }

    double defend() {
        return accuracy * 10 + health * 0.25;
    }

    void display() {
        Hero::display();
        cout << "Bow Type: " << bow << endl;
        cout << "Arrows: " << arrows << endl;
        cout << "Accuracy: " << accuracy << endl;
    }
};

int main() {

    Warrior w("Thor", 120, 50.5, 80, "Axe", 40, 1.5);
    Mage m("Merlin", 90, 60.0, 70, "Fireball", 100, 2.0);
    Archer a("Legolas", 100, 45.0, 75, "Longbow", 60, 1.8);

    w.showGameMessage();

    double wAttack, mAttack, aAttack;

    cout << " Warrior " << endl;
    w.display();
    wAttack = w.attack();
    cout << "Attack Value: " << wAttack << endl;
    cout << "Defense Value: " << w.defend() << endl;

    cout << "\n Mage " << endl;
    m.display();
    mAttack = m.attack();
    cout << "Attack Value: " << mAttack << endl;
    cout << "Defense Value: " << m.defend() << endl;

    cout << "\n Archer " << endl;
    a.display();
    aAttack = a.attack();
    cout << "Attack Value: " << aAttack << endl;
    cout << "Defense Value: " << a.defend() << endl;

    cout << "\n Battle Summary " << endl;

    if (wAttack > mAttack && wAttack > aAttack)
        cout << "Warrior has the highest attack power!" << endl;
    else if (mAttack > wAttack && mAttack > aAttack)
        cout << "Mage has the highest attack power!" << endl;
    else
        cout << "Archer has the highest attack power!" << endl;

    return 0;
}

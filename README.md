# knot-resolver
knot-resolver ansible role

## Examples of playbooks

    ---
    - hosts: localhost
      connection: local
      vars:
        knot_resolver:
          net:
            listen:
             - addresses: "'127.0.0.1'"
               port: 53
               flags: "kind='dns'"
          modules:
           - name: 'hints > iterate'
           - name: 'stats'
           - name: 'predict'
          cache:
            size: '100 * MB'

      roles:
        - knot-resolver


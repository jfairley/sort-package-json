# Snapshot report for `tests/cli.js`

The actual snapshot is saved in `cli.js.snap`.

Generated by [AVA](https://avajs.dev).

## run `cli` with no patterns

> Should format package.json.

    {
      args: [],
      fixtures: [
        {
          expect: `{␊
            "name": "sort-package-json",␊
            "version": "1.0.0"␊
          }`,
          file: 'package.json',
          original: `{␊
            "version": "1.0.0",␊
            "name": "sort-package-json"␊
          }`,
        },
      ],
      result: {
        errorCode: null,
        stderr: '',
        stdout: `package.json is sorted!␊
        `,
      },
    }

## run `cli --check` with no patterns

> Should package.json is not sorted

    {
      args: [
        '--check',
      ],
      fixtures: [
        {
          expect: `{␊
            "version": "1.0.0",␊
            "name": "sort-package-json"␊
          }`,
          file: 'package.json',
          original: `{␊
            "version": "1.0.0",␊
            "name": "sort-package-json"␊
          }`,
        },
      ],
      result: {
        errorCode: 1,
        stderr: '',
        stdout: `package.json␊
        ␊
        1 of 1 matched file is not sorted.␊
        `,
      },
    }

## run `cli -c` with no patterns

> Should support `-c` alias

    {
      args: [
        '-c',
      ],
      fixtures: [
        {
          expect: `{␊
            "version": "1.0.0",␊
            "name": "sort-package-json"␊
          }`,
          file: 'package.json',
          original: `{␊
            "version": "1.0.0",␊
            "name": "sort-package-json"␊
          }`,
        },
      ],
      result: {
        errorCode: 1,
        stderr: '',
        stdout: `package.json␊
        ␊
        1 of 1 matched file is not sorted.␊
        `,
      },
    }

## run `cli` on 1 bad file

> Should format 1 file.

    {
      args: [
        '*/package.json',
      ],
      fixtures: [
        {
          expect: `{␊
            "name": "sort-package-json",␊
            "version": "1.0.0"␊
          }`,
          file: 'bad/package.json',
          original: `{␊
            "version": "1.0.0",␊
            "name": "sort-package-json"␊
          }`,
        },
      ],
      result: {
        errorCode: null,
        stderr: '',
        stdout: `bad/package.json is sorted!␊
        `,
      },
    }

## run `cli --check` on 1 bad file

> Should report 1 file.

    {
      args: [
        '*/package.json',
        '--check',
      ],
      fixtures: [
        {
          expect: `{␊
            "version": "1.0.0",␊
            "name": "sort-package-json"␊
          }`,
          file: 'bad/package.json',
          original: `{␊
            "version": "1.0.0",␊
            "name": "sort-package-json"␊
          }`,
        },
      ],
      result: {
        errorCode: 1,
        stderr: '',
        stdout: `bad/package.json␊
        ␊
        1 of 1 matched file is not sorted.␊
        `,
      },
    }

## run `cli` on 2 bad files

> Should format 2 files.

    {
      args: [
        '*/package.json',
      ],
      fixtures: [
        {
          expect: `{␊
            "name": "sort-package-json",␊
            "version": "1.0.0"␊
          }`,
          file: 'bad-1/package.json',
          original: `{␊
            "version": "1.0.0",␊
            "name": "sort-package-json"␊
          }`,
        },
        {
          expect: `{␊
            "name": "sort-package-json",␊
            "version": "1.0.0"␊
          }`,
          file: 'bad-2/package.json',
          original: `{␊
            "version": "1.0.0",␊
            "name": "sort-package-json"␊
          }`,
        },
      ],
      result: {
        errorCode: null,
        stderr: '',
        stdout: `bad-1/package.json is sorted!␊
        bad-2/package.json is sorted!␊
        `,
      },
    }

## run `cli --check` on 2 bad files

> Should report 2 files.

    {
      args: [
        '*/package.json',
        '--check',
      ],
      fixtures: [
        {
          expect: `{␊
            "version": "1.0.0",␊
            "name": "sort-package-json"␊
          }`,
          file: 'bad-1/package.json',
          original: `{␊
            "version": "1.0.0",␊
            "name": "sort-package-json"␊
          }`,
        },
        {
          expect: `{␊
            "version": "1.0.0",␊
            "name": "sort-package-json"␊
          }`,
          file: 'bad-2/package.json',
          original: `{␊
            "version": "1.0.0",␊
            "name": "sort-package-json"␊
          }`,
        },
      ],
      result: {
        errorCode: 2,
        stderr: '',
        stdout: `bad-1/package.json␊
        bad-2/package.json␊
        ␊
        2 of 2 matched files are not sorted.␊
        `,
      },
    }

## run `cli` on 2 good files and 2 bad files

> Should format 2 files.

    {
      args: [
        '*/package.json',
      ],
      fixtures: [
        {
          expect: `{␊
            "name": "sort-package-json",␊
            "version": "1.0.0"␊
          }`,
          file: 'bad-1/package.json',
          original: `{␊
            "version": "1.0.0",␊
            "name": "sort-package-json"␊
          }`,
        },
        {
          expect: `{␊
            "name": "sort-package-json",␊
            "version": "1.0.0"␊
          }`,
          file: 'bad-2/package.json',
          original: `{␊
            "version": "1.0.0",␊
            "name": "sort-package-json"␊
          }`,
        },
        {
          expect: `{␊
            "name": "sort-package-json",␊
            "version": "1.0.0"␊
          }`,
          file: 'good-1/package.json',
          original: `{␊
            "name": "sort-package-json",␊
            "version": "1.0.0"␊
          }`,
        },
        {
          expect: `{␊
            "name": "sort-package-json",␊
            "version": "1.0.0"␊
          }`,
          file: 'good-2/package.json',
          original: `{␊
            "name": "sort-package-json",␊
            "version": "1.0.0"␊
          }`,
        },
      ],
      result: {
        errorCode: null,
        stderr: '',
        stdout: `bad-1/package.json is sorted!␊
        bad-2/package.json is sorted!␊
        `,
      },
    }

## run `cli --check` on 2 good files and 2 bad files

> Should report 2 files.

    {
      args: [
        '*/package.json',
        '--check',
      ],
      fixtures: [
        {
          expect: `{␊
            "version": "1.0.0",␊
            "name": "sort-package-json"␊
          }`,
          file: 'bad-1/package.json',
          original: `{␊
            "version": "1.0.0",␊
            "name": "sort-package-json"␊
          }`,
        },
        {
          expect: `{␊
            "version": "1.0.0",␊
            "name": "sort-package-json"␊
          }`,
          file: 'bad-2/package.json',
          original: `{␊
            "version": "1.0.0",␊
            "name": "sort-package-json"␊
          }`,
        },
        {
          expect: `{␊
            "name": "sort-package-json",␊
            "version": "1.0.0"␊
          }`,
          file: 'good-1/package.json',
          original: `{␊
            "name": "sort-package-json",␊
            "version": "1.0.0"␊
          }`,
        },
        {
          expect: `{␊
            "name": "sort-package-json",␊
            "version": "1.0.0"␊
          }`,
          file: 'good-2/package.json',
          original: `{␊
            "name": "sort-package-json",␊
            "version": "1.0.0"␊
          }`,
        },
      ],
      result: {
        errorCode: 2,
        stderr: '',
        stdout: `bad-1/package.json␊
        bad-2/package.json␊
        ␊
        2 of 4 matched files are not sorted.␊
        `,
      },
    }

## run `cli` on none exists file

> Should report no files matching.

    {
      args: [
        'NONE_EXISTS_FILE',
      ],
      fixtures: [
        {
          expect: `{␊
            "version": "1.0.0",␊
            "name": "sort-package-json"␊
          }`,
          file: 'package.json',
          original: `{␊
            "version": "1.0.0",␊
            "name": "sort-package-json"␊
          }`,
        },
      ],
      result: {
        errorCode: 1,
        stderr: '',
        stdout: `No matching files.␊
        `,
      },
    }

## run `cli --check` on none exists file

> Should report no files matching.

    {
      args: [
        'NONE_EXISTS_FILE',
        '--check',
      ],
      fixtures: [
        {
          expect: `{␊
            "version": "1.0.0",␊
            "name": "sort-package-json"␊
          }`,
          file: 'package.json',
          original: `{␊
            "version": "1.0.0",␊
            "name": "sort-package-json"␊
          }`,
        },
      ],
      result: {
        errorCode: 1,
        stderr: '',
        stdout: `No matching files.␊
        `,
      },
    }

## run `cli` on duplicate patterns

> Should not format `bad-1/package.json` more than once.

    {
      args: [
        'bad-1/package.json',
        'bad-1/package.json',
        'bad-*/package.json',
        '*/package.json',
      ],
      fixtures: [
        {
          expect: `{␊
            "name": "sort-package-json",␊
            "version": "1.0.0"␊
          }`,
          file: 'bad-1/package.json',
          original: `{␊
            "version": "1.0.0",␊
            "name": "sort-package-json"␊
          }`,
        },
        {
          expect: `{␊
            "name": "sort-package-json",␊
            "version": "1.0.0"␊
          }`,
          file: 'good-1/package.json',
          original: `{␊
            "name": "sort-package-json",␊
            "version": "1.0.0"␊
          }`,
        },
        {
          expect: `{␊
            "name": "sort-package-json",␊
            "version": "1.0.0"␊
          }`,
          file: 'good-2/package.json',
          original: `{␊
            "name": "sort-package-json",␊
            "version": "1.0.0"␊
          }`,
        },
      ],
      result: {
        errorCode: null,
        stderr: '',
        stdout: `bad-1/package.json is sorted!␊
        `,
      },
    }

## run `cli --check` on duplicate patterns

> Should not list `bad-1/package.json` more than once.

    {
      args: [
        'bad-1/package.json',
        'bad-1/package.json',
        'bad-*/package.json',
        '*/package.json',
        '--check',
      ],
      fixtures: [
        {
          expect: `{␊
            "version": "1.0.0",␊
            "name": "sort-package-json"␊
          }`,
          file: 'bad-1/package.json',
          original: `{␊
            "version": "1.0.0",␊
            "name": "sort-package-json"␊
          }`,
        },
        {
          expect: `{␊
            "name": "sort-package-json",␊
            "version": "1.0.0"␊
          }`,
          file: 'good-1/package.json',
          original: `{␊
            "name": "sort-package-json",␊
            "version": "1.0.0"␊
          }`,
        },
        {
          expect: `{␊
            "name": "sort-package-json",␊
            "version": "1.0.0"␊
          }`,
          file: 'good-2/package.json',
          original: `{␊
            "name": "sort-package-json",␊
            "version": "1.0.0"␊
          }`,
        },
      ],
      result: {
        errorCode: 1,
        stderr: '',
        stdout: `bad-1/package.json␊
        ␊
        1 of 3 matched file is not sorted.␊
        `,
      },
    }

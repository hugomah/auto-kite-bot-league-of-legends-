<h1 align="center">
    auto-kite-bot-league-of-legends
</h1>
an autokite/orbwalker league of legend bot made in C#

##What it is !

Nothing much to say about this, it's a program to make you more efficient in the summoner's rift

it's made using basic C sharp implementation, i must admit that i don't really know if it's actually bannable (i personnaly think it anticheat proof) but the best way
to avoid that is to customize it by yourself! The code is open source (it is normally linked to the project by now, i'll show you part of it right under). I've been strongly inspired by a user called -approved-

>https://github.com/approved

My code is basically his with a few changes.

Have Fun while using it

##how to use it

Steps:

1. Launch auto-kite.exe and League of Legends
2. Play rift gamemode
3. Press and hold 'C' to activate the auto walker
4. Deactivate by releasing 'C'

##Files

DirectInputKeys:
```C#
namespace auto-kite
{
    /****************************************************************************
    *
    *      DirectInput keyboard scan codes
    *
    ****************************************************************************/
    public enum DirectInputKeys
    {
        DIK_ESCAPE = 0x01,
        DIK_1 = 0x02,
        DIK_2 = 0x03,
        DIK_3 = 0x04,
        DIK_4 = 0x05,
        DIK_5 = 0x06,
        DIK_6 = 0x07,
        DIK_7 = 0x08,
        DIK_8 = 0x09,
        DIK_9 = 0x0A,
        DIK_0 = 0x0B,
        DIK_MINUS = 0x0C,    /* - on main keyboard */
        DIK_EQUALS = 0x0D,
        DIK_BACK = 0x0E,    /* backspace */
        DIK_TAB = 0x0F,
        DIK_Q = 0x10,
        DIK_W = 0x11,
        DIK_E = 0x12,
        DIK_R = 0x13,
        DIK_T = 0x14,
        DIK_Y = 0x15,
        DIK_U = 0x16,
        DIK_I = 0x17,
        DIK_O = 0x18,
        DIK_P = 0x19,
        DIK_LBRACKET = 0x1A,
        DIK_RBRACKET = 0x1B,
        DIK_RETURN = 0x1C,    /* Enter on main keyboard */
        DIK_LCONTROL = 0x1D,
        DIK_A = 0x1E,
        DIK_S = 0x1F,
        DIK_D = 0x20,
        DIK_F = 0x21,
        DIK_G = 0x22,
        DIK_H = 0x23,
        DIK_J = 0x24,
        DIK_K = 0x25,
        DIK_L = 0x26,
        DIK_SEMICOLON = 0x27,
        DIK_APOSTROPHE = 0x28,
        DIK_GRAVE = 0x29,    /* accent grave */
        DIK_LSHIFT = 0x2A,
        DIK_BACKSLASH = 0x2B,
        DIK_Z = 0x2C,
        DIK_X = 0x2D,
        DIK_C = 0x2E,
        DIK_V = 0x2F,
        DIK_B = 0x30,
        DIK_N = 0x31,
        DIK_M = 0x32,
        DIK_COMMA = 0x33,
        DIK_PERIOD = 0x34,    /* . on main keyboard */
        DIK_SLASH = 0x35,    /* / on main keyboard */
        DIK_RSHIFT = 0x36,
        DIK_MULTIPLY = 0x37,    /* * on numeric keypad */
        DIK_LMENU = 0x38,    /* left Alt */
        DIK_SPACE = 0x39,
        DIK_CAPITAL = 0x3A,
        DIK_F1 = 0x3B,
        DIK_F2 = 0x3C,
        DIK_F3 = 0x3D,
        DIK_F4 = 0x3E,
        DIK_F5 = 0x3F,
        DIK_F6 = 0x40,
        DIK_F7 = 0x41,
        DIK_F8 = 0x42,
        DIK_F9 = 0x43,
        DIK_F10 = 0x44,
        DIK_NUMLOCK = 0x45,
        DIK_SCROLL = 0x46,    /* Scroll Lock */
        DIK_NUMPAD7 = 0x47,
        DIK_NUMPAD8 = 0x48,
        DIK_NUMPAD9 = 0x49,
        DIK_SUBTRACT = 0x4A,    /* - on numeric keypad */
        DIK_NUMPAD4 = 0x4B,
        DIK_NUMPAD5 = 0x4C,
        DIK_NUMPAD6 = 0x4D,
        DIK_ADD = 0x4E,    /* + on numeric keypad */
        DIK_NUMPAD1 = 0x4F,
        DIK_NUMPAD2 = 0x50,
        DIK_NUMPAD3 = 0x51,
        DIK_NUMPAD0 = 0x52,
        DIK_DECIMAL = 0x53,    /* . on numeric keypad */
        DIK_OEM_102 = 0x56,    /* <> or \| on RT 102-key keyboard (Non-U.S.) */
        DIK_F11 = 0x57,
        DIK_F12 = 0x58,
        DIK_F13 = 0x64,    /*                     (NEC PC98) */
        DIK_F14 = 0x65,    /*                     (NEC PC98) */
        DIK_F15 = 0x66,    /*                     (NEC PC98) */
        DIK_KANA = 0x70,    /* (Japanese keyboard)            */
        DIK_ABNT_C1 = 0x73,    /* /? on Brazilian keyboard */
        DIK_CONVERT = 0x79,    /* (Japanese keyboard)            */
        DIK_NOCONVERT = 0x7B,    /* (Japanese keyboard)            */
        DIK_YEN = 0x7D,    /* (Japanese keyboard)            */
        DIK_ABNT_C2 = 0x7E,    /* Numpad . on Brazilian keyboard */
        DIK_NUMPADEQUALS = 0x8D,    /* = on numeric keypad (NEC PC98) */
        DIK_PREVTRACK = 0x90,    /* Previous Track (DIK_CIRCUMFLEX on Japanese keyboard) */
        DIK_AT = 0x91,    /*                     (NEC PC98) */
        DIK_COLON = 0x92,    /*                     (NEC PC98) */
        DIK_UNDERLINE = 0x93,    /*                     (NEC PC98) */
        DIK_KANJI = 0x94,    /* (Japanese keyboard)            */
        DIK_STOP = 0x95,    /*                     (NEC PC98) */
        DIK_AX = 0x96,    /*                     (Japan AX) */
        DIK_UNLABELED = 0x97,    /*                        (J3100) */
        DIK_NEXTTRACK = 0x99,    /* Next Track */
        DIK_NUMPADENTER = 0x9C,    /* Enter on numeric keypad */
        DIK_RCONTROL = 0x9D,
        DIK_MUTE = 0xA0,    /* Mute */
        DIK_CALCULATOR = 0xA1,    /* Calculator */
        DIK_PLAYPAUSE = 0xA2,    /* Play / Pause */
        DIK_MEDIASTOP = 0xA4,    /* Media Stop */
        DIK_VOLUMEDOWN = 0xAE,    /* Volume - */
        DIK_VOLUMEUP = 0xB0,    /* Volume + */
        DIK_WEBHOME = 0xB2,    /* Web home */
        DIK_NUMPADCOMMA = 0xB3,    /* , on numeric keypad (NEC PC98) */
        DIK_DIVIDE = 0xB5,    /* / on numeric keypad */
        DIK_SYSRQ = 0xB7,
        DIK_RMENU = 0xB8,    /* right Alt */
        DIK_PAUSE = 0xC5,    /* Pause */
        DIK_HOME = 0xC7,    /* Home on arrow keypad */
        DIK_UP = 0xC8,    /* UpArrow on arrow keypad */
        DIK_PRIOR = 0xC9,    /* PgUp on arrow keypad */
        DIK_LEFT = 0xCB,    /* LeftArrow on arrow keypad */
        DIK_RIGHT = 0xCD,    /* RightArrow on arrow keypad */
        DIK_END = 0xCF,    /* End on arrow keypad */
        DIK_DOWN = 0xD0,    /* DownArrow on arrow keypad */
        DIK_NEXT = 0xD1,    /* PgDn on arrow keypad */
        DIK_INSERT = 0xD2,    /* Insert on arrow keypad */
        DIK_DELETE = 0xD3,    /* Delete on arrow keypad */
        DIK_LWIN = 0xDB,    /* Left Windows key */
        DIK_RWIN = 0xDC,    /* Right Windows key */
        DIK_APPS = 0xDD,    /* AppMenu key */
        DIK_POWER = 0xDE,    /* System Power */
        DIK_SLEEP = 0xDF,    /* System Sleep */
        DIK_WAKE = 0xE3,    /* System Wake */
        DIK_WEBSEARCH = 0xE5,    /* Web Search */
        DIK_WEBFAVORITES = 0xE6,    /* Web Favorites */
        DIK_WEBREFRESH = 0xE7,    /* Web Refresh */
        DIK_WEBSTOP = 0xE8,    /* Web Stop */
        DIK_WEBFORWARD = 0xE9,    /* Web Forward */
        DIK_WEBBACK = 0xEA,    /* Web Back */
        DIK_MYCOMPUTER = 0xEB,    /* My Computer */
        DIK_MAIL = 0xEC,    /* Mail */
        DIK_MEDIASELECT = 0xED    /* Media Select */
    }
}

```

InputSimulator

```C#
using System;
using System.Runtime.InteropServices;

namespace auto-kite
{
    public static class InputSimulator
    {

        [DllImport("user32.dll", SetLastError = true)]
        private static extern uint SendInput(uint nInputs, Input[] pInputs, int cbSize);

        [DllImport("user32.dll", SetLastError = true)]
        private static extern IntPtr GetMessageExtraInfo();

        [Flags]
        private enum InputType
        {
            Mouse = 0,
            Keyboard = 1,
            Hardware = 2
        }

        [Flags]
        private enum KeyEventF
        {
            KeyDown = 0x0000,
            ExtendedKey = 0x0001,
            KeyUp = 0x0002,
            Unicode = 0x0004,
            Scancode = 0x0008,
        }

        [Flags]
        private enum MouseDataF
        {
            None = 0,
            XButton1 = 0x0001,
            XButton2 = 0x0002
        }

        [Flags]
        private enum MouseEventF
        {
            None = 0,
            Absolute = 0x8000,
            HWheel = 0x1000,
            Move = 0x0001,
            MoveNoCoalesce = 0x2000,
            LeftDown = 0x0002,
            LeftUp = 0x0004,
            RightDown = 0x0008,
            RightUp = 0x0010,
            MiddleDown = 0x0020,
            MiddleUp = 0x0040,
            VirtualDesk = 0x4000,
            Wheel = 0x0800,
            XDown = 0x0080,
            XUp = 0x0100
        }

        private struct Input
        {
            public int type;
            public InputUnion u;
        }

        [StructLayout(LayoutKind.Explicit)]
        private struct InputUnion
        {
            [FieldOffset(0)] public MouseInput mi;
            [FieldOffset(0)] public KeyboardInput ki;
            [FieldOffset(0)] public readonly HardwareInput hi;
        }

        [StructLayout(LayoutKind.Sequential)]
        private struct MouseInput
        {
            public readonly int dx;
            public readonly int dy;
            public uint mouseData;
            public uint dwFlags;
            public readonly uint time;
            public IntPtr dwExtraInfo;
        }

        [StructLayout(LayoutKind.Sequential)]
        private struct KeyboardInput
        {
            public ushort wVk;
            public ushort wScan;
            public uint dwFlags;
            public readonly uint time;
            public IntPtr dwExtraInfo;
        }

        [StructLayout(LayoutKind.Sequential)]
        private struct HardwareInput
        {
            public readonly uint uMsg;
            public readonly ushort wParamL;
            public readonly ushort wParamH;
        }

        public static class Keyboard
        {
            public static void KeyDown(ushort keycode)
            {
                Input[] inputs =
                {
                            new Input
                            {
                                type = (int) InputType.Keyboard,
                                u = new InputUnion
                                {
                                    ki = new KeyboardInput
                                    {
                                        wVk = 0,
                                        wScan = keycode,
                                        dwFlags = (uint) (KeyEventF.KeyDown | KeyEventF.Scancode),
                                        dwExtraInfo = GetMessageExtraInfo()
                                    }
                                }
                            }
                        };

                SendInput((uint)inputs.Length, inputs, Marshal.SizeOf(typeof(Input)));
            }

            public static void KeyUp(ushort keycode)
            {
                Input[] inputs =
                {
                            new Input
                            {
                                type = (int) InputType.Keyboard,
                                u = new InputUnion
                                {
                                    ki = new KeyboardInput
                                    {
                                        wVk = 0,
                                        wScan = keycode,
                                        dwFlags = (uint) (KeyEventF.KeyUp | KeyEventF.Scancode),
                                        dwExtraInfo = GetMessageExtraInfo()
                                    }
                                }
                            }
                        };

                SendInput((uint)inputs.Length, inputs, Marshal.SizeOf(typeof(Input)));
            }

            public static void KeyPress(ushort keycode)
            {
                KeyDown(keycode);
                KeyUp(keycode);
            }
        }

        public static class Mouse
        {
            public enum Buttons
            {
                Left,
                Right,
                Middle,
                X1,
                X2
            }

            public static void MouseDown(Buttons button)
            {

                MouseEventF flags;
                MouseDataF data;

                (flags, data) = button switch
                {
                    Buttons.Left => (MouseEventF.LeftDown, MouseDataF.None),
                    Buttons.Right => (MouseEventF.RightDown, MouseDataF.None),
                    Buttons.Middle => (MouseEventF.MiddleDown, MouseDataF.None),
                    Buttons.X1 => (MouseEventF.XDown, MouseDataF.XButton1),
                    Buttons.X2 => (MouseEventF.XDown, MouseDataF.XButton2),
                    _ => throw new Exception("Unknown button type"),
                };

                Input[] inputs =
                {
                            new Input
                            {
                                type = (int) InputType.Mouse,
                                u = new InputUnion
                                {
                                    mi = new MouseInput
                                    {
                                        mouseData = (uint)data,
                                        dwFlags = (uint)flags,
                                        dwExtraInfo = GetMessageExtraInfo()
                                    }
                                }
                            }
                        };

                SendInput((uint)inputs.Length, inputs, Marshal.SizeOf(typeof(Input)));
            }

            public static void MouseUp(Buttons button)
            {

                MouseEventF flags;
                MouseDataF data;

                (flags, data) = button switch
                {
                    Buttons.Left => (MouseEventF.LeftUp, MouseDataF.None),
                    Buttons.Right => (MouseEventF.RightUp, MouseDataF.None),
                    Buttons.Middle => (MouseEventF.MiddleUp, MouseDataF.None),
                    Buttons.X1 => (MouseEventF.XUp, MouseDataF.XButton1),
                    Buttons.X2 => (MouseEventF.XUp, MouseDataF.XButton2),
                    _ => throw new Exception("Unknown button type"),
                };

                Input[] inputs =
                {
                            new Input
                            {
                                type = (int) InputType.Mouse,
                                u = new InputUnion
                                {
                                    mi = new MouseInput
                                    {
                                        mouseData = (uint)data,
                                        dwFlags = (uint)flags,
                                        dwExtraInfo = GetMessageExtraInfo()
                                    }
                                }
                            }
                        };

                SendInput((uint)inputs.Length, inputs, Marshal.SizeOf(typeof(Input)));
            }

            public static void MouseClick(Buttons button)
            {
                MouseDown(button);
                MouseUp(button);
            }

            public static void MouseDoubleClick(Buttons button)
            {
                MouseClick(button);
                MouseClick(button);
            }
        }
    }
}

```

Program

```C#
using LowLevelInput.Hooks;
using Newtonsoft.Json.Linq;
using System;
using System.Diagnostics;
using System.IO;
using System.Linq;
using System.Net;
using System.Runtime.InteropServices;
using System.Timers;

namespace auto-kite
{
    public class Program
    {
        [DllImport("user32.dll")]
        private static extern IntPtr GetForegroundWindow();

        private const string ActivePlayerEndpoint = @"https://127.0.0.1:2999/liveclientdata/activeplayer";
        private const string PlayerListEndpoint = @"https://127.0.0.1:2999/liveclientdata/playerlist";
        private const string ChampionStatsEndpoint = @"https://raw.communitydragon.org/latest/game/data/characters/";
        private const string SettingsFile = @"settings\settings.json";

        private static bool HasProcess = false;
        private static bool IsExiting = false;
        private static bool IsIntializingValues = false;
        private static bool IsUpdatingAttackValues = false;

        private static readonly Settings CurrentSettings = new Settings();
        private static readonly WebClient Client = new WebClient();
        private static readonly InputManager InputManager = new InputManager();
        private static Process LeagueProcess = null;

        private static readonly Timer OrbWalkTimer = new Timer(100d / 3d);

        private static bool OrbWalkerTimerActive = false;

        private static string ActivePlayerName = string.Empty;
        private static string ChampionName = string.Empty;
        private static string RawChampionName = string.Empty;

        private static double ClientAttackSpeed = 0.625;
        private static double ChampionAttackCastTime = 0.625;
        private static double ChampionAttackTotalTime = 0.625;
        private static double ChampionAttackSpeedRatio = 0.625;
        private static double ChampionAttackDelayPercent = 0.3;
        private static double ChampionAttackDelayScaling = 1.0;

        /// <summary>
        /// This is a buffer to prevent you from accidentally canceling your auto-attack too soon, as a result of fps, ping, or otherwise.
        /// </summary>
        private static readonly double WindupBuffer = 1d / 15d;

        // If we're trying to input faster than this, don't
        private static readonly double MinInputDelay = 1d / 30d;

        // This is honestly just semi-random because we need an interval to run the timer at
        private static readonly double OrderTickRate = 1d / 30d;

#if DEBUG
        private static int TimerCallbackCounter = 0;
#endif

        // These are all in seconds
        public static double GetSecondsPerAttack() => 1 / ClientAttackSpeed;
        public static double GetWindupDuration() => (((GetSecondsPerAttack() * ChampionAttackDelayPercent) - ChampionAttackCastTime) * ChampionAttackDelayScaling) + ChampionAttackCastTime;
        public static double GetBufferedWindupDuration() => GetWindupDuration() + WindupBuffer;

        public static void Main(string[] args)
        {
            if (!File.Exists(SettingsFile))
            {
                Directory.CreateDirectory("settings");
                CurrentSettings.CreateNew(SettingsFile);
            }
            else
            {
                CurrentSettings.Load(SettingsFile);
            }

            ServicePointManager.ServerCertificateValidationCallback += (sender, cert, chain, sslPolicyErrors) => true;
            Client.Proxy = null;

            Console.Clear();
            Console.CursorVisible = false;

            InputManager.Initialize();
            InputManager.OnKeyboardEvent += InputManager_OnKeyboardEvent;
            InputManager.OnMouseEvent += InputManager_OnMouseEvent;

            OrbWalkTimer.Elapsed += OrbWalkTimer_Elapsed;
#if DEBUG
            Timer callbackTimer = new Timer(16.66);
            callbackTimer.Elapsed += Timer_CallbackLog;
#endif

            Timer attackSpeedCacheTimer = new Timer(OrderTickRate);
            attackSpeedCacheTimer.Elapsed += AttackSpeedCacheTimer_Elapsed;

            attackSpeedCacheTimer.Start();
            Console.WriteLine($"Press and hold '{(VirtualKeyCode)CurrentSettings.ActivationKey}' to activate the Orb Walker");

            CheckLeagueProcess();

            Console.ReadLine();
        }

#if DEBUG
        private static void Timer_CallbackLog(object sender, ElapsedEventArgs e)
        {
            if (TimerCallbackCounter > 1 || TimerCallbackCounter < 0)
            {
                Console.Clear();
                Console.WriteLine("Timer Error Detected");
                throw new Exception("Timers must not run simultaneously");
            }
        }
#endif

        private static void InputManager_OnMouseEvent(VirtualKeyCode key, KeyState state, int x, int y)
        {
        }

        private static void InputManager_OnKeyboardEvent(VirtualKeyCode key, KeyState state)
        {
            if (key == (VirtualKeyCode)CurrentSettings.ActivationKey)
            {
                switch (state)
                {
                    case KeyState.Down when !OrbWalkerTimerActive:
                        OrbWalkerTimerActive = true;
                        OrbWalkTimer.Start();
                        break;

                    case KeyState.Up when OrbWalkerTimerActive:
                        OrbWalkerTimerActive = false;
                        OrbWalkTimer.Stop();
                        break;
                }
            }
        }

        // When these DateTime instances are in the past, the action they gate can be taken
        private static DateTime nextInput = default;
        private static DateTime nextMove = default;
        private static DateTime nextAttack = default;

        private static readonly Stopwatch owStopWatch = new Stopwatch();

        private static void OrbWalkTimer_Elapsed(object sender, ElapsedEventArgs e)
        {
#if DEBUG
            owStopWatch.Start();
            TimerCallbackCounter++;
#endif
            if (!HasProcess || IsExiting || GetForegroundWindow() != LeagueProcess.MainWindowHandle)
            {
#if DEBUG
                TimerCallbackCounter--;
#endif

                return;
            }

            // Store time at timer tick start into a variable for readability
            var time = e.SignalTime;

            // Make sure we can send input without being dropped
            // This is used for gating movement orders when waiting for an attack to be prepared
            // This is not needed if this function is not ran frequently enough for it to matter
            // If it isn't, you might end up with this timer and this function's timer being out of sync
            //   resulting in a (worst-case) OrderTickRate + MinInputDelay delay
            // It is currently disabled due to this, enable it if you want/need to
            if (true || nextInput < time)
            {
                // If we can attack, do so
                if (nextAttack < time)
                {
                    // Store current time + input delay so we're aware when we can move next
                    nextInput = time.AddSeconds(MinInputDelay);

                    // Send attack input
                    InputSimulator.Keyboard.KeyDown((ushort)DirectInputKeys.DIK_A);
                    InputSimulator.Mouse.MouseClick(InputSimulator.Mouse.Buttons.Left);
                    InputSimulator.Keyboard.KeyUp((ushort)DirectInputKeys.DIK_A);

                    // We've sent input now, so we're re-fetching time as I have no idea how long input takes
                    // I'm assuming it's negligable, but why not
                    // Please check what the actual difference is if you consider keeping this lol
                    var attackTime = DateTime.Now;

                    // Store timings for when to next attack / move
                    nextMove = attackTime.AddSeconds(GetBufferedWindupDuration());
                    nextAttack = attackTime.AddSeconds(GetSecondsPerAttack());
                }
                // If we can't attack but we can move, do so
                else if (nextMove < time)
                {
                    // Store current time + input delay so we're aware when we can attack / move next
                    nextInput = time.AddSeconds(MinInputDelay);

                    // Send move input
                    InputSimulator.Mouse.MouseClick(InputSimulator.Mouse.Buttons.Right);
                }
            }
#if DEBUG
            TimerCallbackCounter--;
            owStopWatch.Reset();
#endif
        }

        private static void CheckLeagueProcess()
        {
            while (LeagueProcess is null || !HasProcess)
            {
                LeagueProcess = Process.GetProcessesByName("League of Legends").FirstOrDefault();
                if (LeagueProcess is null || LeagueProcess.HasExited)
                {
                    continue;
                }
                HasProcess = true;
                LeagueProcess.EnableRaisingEvents = true;
                LeagueProcess.Exited += LeagueProcess_Exited;
            }
        }

        private static void LeagueProcess_Exited(object sender, EventArgs e)
        {
            HasProcess = false;
            LeagueProcess = null;
            //Console.Clear();
            Console.WriteLine("League Process Exited");
            CheckLeagueProcess();
        }

        private static void AttackSpeedCacheTimer_Elapsed(object sender, ElapsedEventArgs e)
        {
            if (HasProcess && !IsExiting && !IsIntializingValues && !IsUpdatingAttackValues)
            {
                IsUpdatingAttackValues = true;

                JToken activePlayerToken = null;
                try
                {
                    activePlayerToken = JToken.Parse(Client.DownloadString(ActivePlayerEndpoint));
                }
                catch
                {
                    IsUpdatingAttackValues = false;
                    return;
                }

                if (string.IsNullOrEmpty(ChampionName))
                {
                    ActivePlayerName = activePlayerToken?["summonerName"].ToString();
                    IsIntializingValues = true;
                    JToken playerListToken = JToken.Parse(Client.DownloadString(PlayerListEndpoint));
                    foreach (JToken token in playerListToken)
                    {
                        if (token["summonerName"].ToString().Equals(ActivePlayerName))
                        {
                            ChampionName = token["championName"].ToString();
                            string[] rawNameArray = token["rawChampionName"].ToString().Split('_', StringSplitOptions.RemoveEmptyEntries);
                            RawChampionName = rawNameArray[^1];
                        }
                    }

                    if (!GetChampionBaseValues(RawChampionName))
                    {
                        IsIntializingValues = false;
                        IsUpdatingAttackValues = false;
                        return;
                    }

#if DEBUG
                    Console.Title = $"({ActivePlayerName}) {ChampionName}";
#endif

                    IsIntializingValues = false;
                }

#if DEBUG
                Console.SetCursorPosition(0, 0);
                Console.WriteLine($"{owStopWatch.ElapsedMilliseconds}\n" +
                    $"Attack Speed Ratio: {ChampionAttackSpeedRatio}\n" +
                    $"Windup Percent: {ChampionAttackDelayPercent}\n" +
                    $"Current AS: {ClientAttackSpeed:0.00####}\n" +
                    $"Seconds Per Attack: {GetSecondsPerAttack():0.00####}\n" +
                    $"Windup Duration: {GetWindupDuration():0.00####}s + {WindupBuffer}s delay\n" +
                    $"Attack Down Time: {(GetSecondsPerAttack() - GetWindupDuration()):0.00####}s");
#endif

                ClientAttackSpeed = activePlayerToken["championStats"]["attackSpeed"].Value<double>();
                IsUpdatingAttackValues = false;
            }
        }

        private static bool GetChampionBaseValues(string championName)
        {
            string lowerChampionName = championName.ToLower();
            JToken championBinToken = null;
            try
            {
                championBinToken = JToken.Parse(Client.DownloadString($"{ChampionStatsEndpoint}{lowerChampionName}/{lowerChampionName}.bin.json"));
            }
            catch
            {
                return false;
            }
            JToken championRootStats = championBinToken[$"Characters/{championName}/CharacterRecords/Root"];
            ChampionAttackSpeedRatio = championRootStats["attackSpeedRatio"].Value<double>(); ;

            JToken championBasicAttackInfoToken = championRootStats["basicAttack"];
            JToken championAttackDelayOffsetToken = championBasicAttackInfoToken["mAttackDelayCastOffsetPercent"];
            JToken championAttackDelayOffsetSpeedRatioToken = championBasicAttackInfoToken["mAttackDelayCastOffsetPercentAttackSpeedRatio"];

            if (championAttackDelayOffsetSpeedRatioToken?.Value<double?>() != null)
            {
                ChampionAttackDelayScaling = championAttackDelayOffsetSpeedRatioToken.Value<double>();
            }

            if (championAttackDelayOffsetToken?.Value<double?>() == null)
            {
                JToken attackTotalTimeToken = championBasicAttackInfoToken["mAttackTotalTime"];
                JToken attackCastTimeToken = championBasicAttackInfoToken["mAttackCastTime"];

                if (attackTotalTimeToken?.Value<double?>() == null && attackCastTimeToken?.Value<double?>() == null)
                {
                    string attackName = championBasicAttackInfoToken["mAttackName"].ToString();
                    string attackSpell = $"Characters/{attackName.Split(new[] { "BasicAttack" }, StringSplitOptions.RemoveEmptyEntries)[0]}/Spells/{attackName}";
                    ChampionAttackDelayPercent += championBinToken[attackSpell]["mSpell"]["delayCastOffsetPercent"].Value<double>();
                }
                else
                {
                    ChampionAttackTotalTime = attackTotalTimeToken.Value<double>();
                    ChampionAttackCastTime = attackCastTimeToken.Value<double>(); ;

                    ChampionAttackDelayPercent = ChampionAttackCastTime / ChampionAttackTotalTime;
                }
            }
            else
            {
                ChampionAttackDelayPercent += championAttackDelayOffsetToken.Value<double>(); ;
            }

            return true;
        }
    }
}

```

Settings


```C#
using LowLevelInput.Hooks;
using Newtonsoft.Json;
using System;
using System.Collections.Generic;
using System.IO;
using System.Text;

namespace auto-kite
{
    public class Settings
    {
        public int ActivationKey { get; set; } = (int)VirtualKeyCode.C;

        public void CreateNew(string path)
        {
            using (StreamWriter sw = new StreamWriter(File.Create(path)))
            {
                sw.WriteLine("/* All Corresponding Key Bind Key Codes");
                foreach (int i in Enum.GetValues(typeof(VirtualKeyCode)))
                {
                    sw.WriteLine($"* \t{i} - {(VirtualKeyCode)i}");
                }
                sw.WriteLine("*/");
                sw.WriteLine(JsonConvert.SerializeObject(this));
            }
        }

        public void Load(string path)
        {
            ActivationKey = JsonConvert.DeserializeObject<Settings>(File.ReadAllText(path)).ActivationKey;
        }
    }
}

```

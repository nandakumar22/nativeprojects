# nativeprojects


import React from 'react';
import { View, SafeAreaView, TouchableOpacity, Text, Image } from 'react-native';
import { BaseComponent } from '../CC';
import { ViewStyles } from '../../resources/Theme';
class VMNetwork2 extends BaseComponent {

    constructor(props) {
        super(props);
        this.state = {
            orientation: ViewStyles.isPortrait() ? 'portrait' : 'landscape',
            index: 1

        };
    }


    changeindex = (index) => {
        this.setState({ index })
    }

    renderFirstComponent() {
        const styles = this.styleSheet();
        if (this.state.index == 1) {
            return (
                <View style={styles.networkviewstyle}>
                    <View style={this.props.vmNetworkContainerViewStyle}>
                        <Text style={[styles.networkTitleStyle, this.props.vmTextnetworkTitleTextStyle]}> {this.localStrings('networkTitle')}</Text>
                        {this.renderSeperator(styles)}

                        <View style={styles.networklogos}>
                            <Image></Image>
                        </View>
                        <Text style={[styles.noNetworkMessageStyle, this.props.vmTextnoNetworkMessageTextStyle]}>{this.props.vmTextnoNetworkMessageTxt}</Text>
                        <TouchableOpacity style={styles.button1style} onPress={() => this.changeindex(2)}>
                            <Text style={{ textAlign: 'center', color: 'white', fontSize: 17 }}>FirstPage</Text>
                        </TouchableOpacity>
                    </View>
                </View>
            );
        }
    }


    renderSecondComponent() {
        const styles = this.styleSheet();
        if (this.state.index == 2) {
            return (
                <View style={styles.networkviewstyle}>
                    <View style={this.props.vmNetworkContainerViewStyle}>
                        <Text style={[styles.networkTitleStyle, this.props.vmTextnetworkTitleTextStyle]}> {this.localStrings('networkTitle')}</Text>
                        {this.renderSeperator(styles)}

                        <View style={styles.networklogos}>
                            <Image></Image>
                        </View>
                        <Text style={[styles.noNetworkMessageStyle, this.props.vmTextnoNetworkMessageTextStyle]}>{this.props.vmTextnoNetworkMessageTxt}</Text>

                        <Text style={[styles.noNetworkMessageStyle, this.props.vmTextnoNetworkMessageTextStyle]}>{this.props.vmTextnoNetworkMessageTxt}</Text>
                        <TouchableOpacity style={styles.button2style}
                            onPress={() => this.changeindex(3)}>
                            <Text style={{ textAlign: 'center', color: 'white', fontSize: 17 }}>SecondPage</Text>
                        </TouchableOpacity>
                    </View>
                </View>
            )
        }
    }

    renderThirdComponent() {
        const styles = this.styleSheet();
        if (this.state.index == 3) {
            return (

                <View style={styles.networkviewstyle}>
                    <View style={this.props.vmNetworkContainerViewStyle}>
                        <Text style={[styles.networkTitleStyle, this.props.vmTextnetworkTitleTextStyle]}> {this.localStrings('networkTitle')}</Text>
                        {this.renderSeperator(styles)}
                        <View style={styles.networklogos}>
                            <Image></Image>
                        </View>
                        <Text style={[styles.noNetworkMessageStyle, this.props.vmTextnoNetworkMessageTextStyle]}>{this.props.vmTextnoNetworkMessageTxt}</Text>

                        <TouchableOpacity style={styles.button3style}
                            onPress={() => this.changeindex(1)}>
                            <Text style={{ textAlign: 'center', color: 'white', fontSize: 17 }}>ThirdPage</Text>
                        </TouchableOpacity>
                    </View>
                </View>

            )
        }
    }


    renderSeperator(styles) {
        return <View style={styles.seperatorViewStyle} />;
    }

    render() {
        const styles = this.styleSheet();
        return (

            <SafeAreaView style={styles.safeAreaContainerStyle}>
                {this.renderFirstComponent()}
                {this.renderSecondComponent()}
                {this.renderThirdComponent()}
            </SafeAreaView>
        );
    }

    defaultStyles() {
        const { Colors, ViewStyles, Fonts } = this.theme();
        return {
            safeAreaContainerStyle: {
                ...ViewStyles.safeAreaContainerStyle,
                backgroundColor: Colors.TEXT_WHITE_COLOR,
            },
            networkviewstyle: {
                justifyContent: 'center',
                alignSelf: 'center',
                backgroundColor: Colors.TEXT_WHITE_COLOR,
                borderColor: Colors.SHADOW_COLOR,
                borderRadius: 12,
                shadowColor: Colors.SHADOW_COLOR,
                shadowOffset: { width: 0, height: 4 },
                shadowRadius: 4,
                shadowOpacity: 0.5,
                width: 594,
                height: 472,
            },
            networkTitleStyle: {
                color: Colors.PURE_BLACK,
                ...Fonts.Barlow_Regular(21),
                left: 35,
                bottom: ViewStyles.heightNormalize(55)
            },
            seperatorViewStyle: {
                alignSelf: 'center',
                width: 435,
                height: 1,
                backgroundColor: Colors.SEPERATOR_COLOR,
                bottom: ViewStyles.heightNormalize(28),
                Opacity: 0.28
            },
            networklogos: {
                width: 40.69,
                height: 45.93,
                backgroundColor: Colors.SEPERATOR_COLOR,
                position: 'absolute',
                justifyContent: 'center',
                alignSelf: 'center'
            },
            button1style: {
                height: 40,
                width: "30%",
                backgroundColor: Colors.TEXT_RED_COLOR,
                position: 'absolute',
                justifyContent: 'center',
                alignSelf: 'center',
                top: ViewStyles.heightNormalize(80),
                borderRadius: 12
            },
            button2style: {
                height: 40,
                width: "30%",
                backgroundColor: 'blue',
                position: 'absolute',
                justifyContent: 'center',
                alignSelf: 'center',
                top: ViewStyles.heightNormalize(80),
                borderRadius: 12
            },
            button3style: {
                height: 40,
                width: "30%",
                backgroundColor: 'green',
                position: 'absolute',
                justifyContent: 'center',
                alignSelf: 'center',
                top: ViewStyles.heightNormalize(80),
                borderRadius: 12
            },
            noNetworkMessageStyle: {
                color: Colors.PURE_BLACK,
                textAlign: 'center',
                ...Fonts.Barlow_Regular(21),
                textAlign: 'center',
                justifyContent: 'center',
                top: ViewStyles.heightNormalize(40)
            },
        }
    }
}

export default VMNetwork2;

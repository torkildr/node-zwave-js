## API Report File for "@zwave-js/testing"

> Do not edit this file. It is a report generated by [API Extractor](https://api-extractor.com/).

```ts

/// <reference types="jest" />
/// <reference types="node" />

import { CommandClasses } from '@zwave-js/core';
import { CommandClassInfo } from '@zwave-js/core';
import { FunctionType } from '@zwave-js/serial/safe';
import { ICommandClass } from '@zwave-js/core';
import { Message } from '@zwave-js/serial';
import type { MockPortBinding } from '@zwave-js/serial/mock';
import { NodeProtocolInfoAndDeviceClass } from '@zwave-js/core';
import Transport from 'winston-transport';
import { ZWaveApiVersion } from '@zwave-js/core/safe';
import type { ZWaveHost } from '@zwave-js/host';
import { ZWaveLibraryTypes } from '@zwave-js/core/safe';
import type { ZWaveLogInfo } from '@zwave-js/core';

// Warning: (ae-missing-release-tag) "assertLogInfo" is exported by the package, but it is missing a release tag (@alpha, @beta, @public, or @internal)
//
// @public (undocumented)
export function assertLogInfo(transport: SpyTransport, options: Partial<{
    level: string;
    predicate: (info: ZWaveLogInfo) => boolean;
    callNumber: number;
}>): void;

// Warning: (ae-missing-release-tag) "assertMessage" is exported by the package, but it is missing a release tag (@alpha, @beta, @public, or @internal)
//
// @public
export function assertMessage(transport: SpyTransport, options: Partial<{
    message: string;
    predicate: (msg: string) => boolean;
    ignoreColor: boolean;
    ignoreTimestamp: boolean;
    ignoreChannel: boolean;
    callNumber: number;
}>): void;

// Warning: (ae-missing-release-tag) "createMockZWaveAckFrame" is exported by the package, but it is missing a release tag (@alpha, @beta, @public, or @internal)
//
// @public (undocumented)
export function createMockZWaveAckFrame(options?: Partial<Omit<MockZWaveAckFrame, "direction" | "payload">>): MockZWaveAckFrame;

// Warning: (ae-missing-release-tag) "createMockZWaveRequestFrame" is exported by the package, but it is missing a release tag (@alpha, @beta, @public, or @internal)
//
// @public (undocumented)
export function createMockZWaveRequestFrame(payload: ICommandClass, options?: Partial<Omit<MockZWaveRequestFrame, "direction" | "payload">>): MockZWaveRequestFrame;

// Warning: (ae-missing-release-tag) "MOCK_FRAME_ACK_TIMEOUT" is exported by the package, but it is missing a release tag (@alpha, @beta, @public, or @internal)
//
// @public
export const MOCK_FRAME_ACK_TIMEOUT = 1000;

// Warning: (ae-missing-release-tag) "MockController" is exported by the package, but it is missing a release tag (@alpha, @beta, @public, or @internal)
// Warning: (ae-unresolved-link) The @link reference could not be resolved: The package "@zwave-js/testing" does not have an export "MockSerialPort"
//
// @public
export class MockController {
    constructor(options: MockControllerOptions);
    ackNodeRequestFrame(node: MockNode, frame?: MockZWaveRequestFrame): Promise<void>;
    // (undocumented)
    addNode(node: MockNode): void;
    assertReceivedHostMessage(predicate: (msg: Message) => boolean, options?: {
        errorMessage?: string;
    }): void;
    autoAckNodeFrames: boolean;
    // Warning: (ae-forgotten-export) The symbol "MockControllerCapabilities" needs to be exported by the entry point index.d.ts
    //
    // (undocumented)
    readonly capabilities: MockControllerCapabilities;
    clearReceivedHostMessages(): void;
    // (undocumented)
    defineBehavior(...behaviors: MockControllerBehavior[]): void;
    // Warning: (tsdoc-param-tag-missing-hyphen) The @param block should be followed by a parameter name and then a hyphen
    expectHostACK(timeout: number): Promise<void>;
    // Warning: (tsdoc-param-tag-missing-hyphen) The @param block should be followed by a parameter name and then a hyphen
    expectHostMessage(timeout: number, predicate: (msg: Message) => boolean): Promise<Message>;
    // Warning: (tsdoc-param-tag-missing-hyphen) The @param block should be followed by a parameter name and then a hyphen
    expectNodeACK(node: MockNode, timeout: number): Promise<MockZWaveAckFrame>;
    // Warning: (tsdoc-param-tag-missing-hyphen) The @param block should be followed by a parameter name and then a hyphen
    expectNodeCC<T extends ICommandClass = ICommandClass>(node: MockNode, timeout: number, predicate: (cc: ICommandClass) => cc is T): Promise<T>;
    // Warning: (tsdoc-param-tag-missing-hyphen) The @param block should be followed by a parameter name and then a hyphen
    expectNodeFrame<T extends MockZWaveFrame = MockZWaveFrame>(node: MockNode, timeout: number, predicate: (msg: MockZWaveFrame) => msg is T): Promise<T>;
    // (undocumented)
    readonly host: ZWaveHost;
    // (undocumented)
    get nodes(): ReadonlyMap<number, MockNode>;
    onNodeFrame(node: MockNode, frame: MockZWaveFrame): Promise<void>;
    // (undocumented)
    removeNode(node: MockNode): void;
    sendToHost(data: Buffer): Promise<void>;
    sendToNode(node: MockNode, frame: MockZWaveFrame): Promise<MockZWaveAckFrame | undefined>;
    // (undocumented)
    readonly serial: MockPortBinding;
    readonly state: Map<string, unknown>;
}

// Warning: (ae-missing-release-tag) "MockControllerBehavior" is exported by the package, but it is missing a release tag (@alpha, @beta, @public, or @internal)
//
// @public (undocumented)
export interface MockControllerBehavior {
    onHostMessage?: (host: ZWaveHost, controller: MockController, msg: Message) => Promise<boolean | undefined> | boolean | undefined;
    onNodeFrame?: (host: ZWaveHost, controller: MockController, node: MockNode, frame: MockZWaveFrame) => Promise<boolean | undefined> | boolean | undefined;
}

// Warning: (ae-missing-release-tag) "MockControllerOptions" is exported by the package, but it is missing a release tag (@alpha, @beta, @public, or @internal)
//
// @public (undocumented)
export interface MockControllerOptions {
    // (undocumented)
    capabilities?: Partial<MockControllerCapabilities>;
    // (undocumented)
    homeId?: number;
    // (undocumented)
    ownNodeId?: number;
    // (undocumented)
    serial: MockPortBinding;
}

// Warning: (ae-missing-release-tag) "MockEndpoint" is exported by the package, but it is missing a release tag (@alpha, @beta, @public, or @internal)
//
// @public (undocumented)
export class MockEndpoint {
    constructor(options: MockEndpointOptions);
    addCC(cc: CommandClasses, info: Partial<CommandClassInfo>): void;
    // Warning: (ae-forgotten-export) The symbol "MockEndpointCapabilities" needs to be exported by the entry point index.d.ts
    //
    // (undocumented)
    readonly capabilities: MockEndpointCapabilities;
    // (undocumented)
    readonly implementedCCs: Map<CommandClasses, CommandClassInfo>;
    // (undocumented)
    readonly index: number;
    // (undocumented)
    readonly node: MockNode;
    removeCC(cc: CommandClasses): void;
}

// Warning: (ae-missing-release-tag) "MockEndpointOptions" is exported by the package, but it is missing a release tag (@alpha, @beta, @public, or @internal)
//
// @public (undocumented)
export interface MockEndpointOptions {
    // (undocumented)
    capabilities?: Partial<MockEndpointCapabilities> & {
        commandClasses?: PartialCCCapabilities[];
    };
    // (undocumented)
    index: number;
    // (undocumented)
    node: MockNode;
}

// Warning: (ae-missing-release-tag) "MockNode" is exported by the package, but it is missing a release tag (@alpha, @beta, @public, or @internal)
//
// @public
export class MockNode {
    constructor(options: MockNodeOptions);
    ackControllerRequestFrame(frame?: MockZWaveRequestFrame): Promise<void>;
    addCC(cc: CommandClasses, info: Partial<CommandClassInfo>): void;
    assertReceivedControllerFrame(predicate: (frame: MockZWaveFrame) => boolean, options?: {
        noMatch?: boolean;
        errorMessage?: string;
    }): void;
    assertSentControllerFrame(predicate: (frame: MockZWaveFrame) => boolean, options?: {
        noMatch?: boolean;
        errorMessage?: string;
    }): void;
    autoAckControllerFrames: boolean;
    // Warning: (ae-forgotten-export) The symbol "MockNodeCapabilities" needs to be exported by the entry point index.d.ts
    //
    // (undocumented)
    readonly capabilities: MockNodeCapabilities;
    clearReceivedControllerFrames(): void;
    clearSentControllerFrames(): void;
    // (undocumented)
    readonly controller: MockController;
    // (undocumented)
    defineBehavior(...behaviors: MockNodeBehavior[]): void;
    // (undocumented)
    readonly endpoints: Map<number, MockEndpoint>;
    // Warning: (tsdoc-param-tag-missing-hyphen) The @param block should be followed by a parameter name and then a hyphen
    expectControllerACK(timeout: number): Promise<MockZWaveAckFrame>;
    // Warning: (tsdoc-param-tag-missing-hyphen) The @param block should be followed by a parameter name and then a hyphen
    expectControllerFrame<T extends MockZWaveFrame = MockZWaveFrame>(timeout: number, predicate: (msg: MockZWaveFrame) => msg is T): Promise<T>;
    // (undocumented)
    readonly id: number;
    // (undocumented)
    readonly implementedCCs: Map<CommandClasses, CommandClassInfo>;
    onControllerFrame(frame: MockZWaveFrame): Promise<void>;
    removeCC(cc: CommandClasses): void;
    sendToController(frame: MockZWaveFrame): Promise<MockZWaveAckFrame | undefined>;
    readonly state: Map<string, unknown>;
}

// Warning: (ae-missing-release-tag) "MockNodeBehavior" is exported by the package, but it is missing a release tag (@alpha, @beta, @public, or @internal)
//
// @public (undocumented)
export interface MockNodeBehavior {
    onControllerFrame?: (controller: MockController, self: MockNode, frame: MockZWaveFrame) => Promise<boolean | undefined> | boolean | undefined;
}

// Warning: (ae-missing-release-tag) "MockNodeOptions" is exported by the package, but it is missing a release tag (@alpha, @beta, @public, or @internal)
//
// @public (undocumented)
export interface MockNodeOptions {
    // (undocumented)
    capabilities?: Partial<MockNodeCapabilities> & {
        commandClasses?: PartialCCCapabilities[];
        endpoints?: (Partial<MockEndpointCapabilities> & {
            commandClasses?: PartialCCCapabilities[];
        })[];
    };
    // (undocumented)
    controller: MockController;
    // (undocumented)
    id: number;
}

// Warning: (ae-missing-release-tag) "MockZWaveAckFrame" is exported by the package, but it is missing a release tag (@alpha, @beta, @public, or @internal)
//
// @public (undocumented)
export interface MockZWaveAckFrame {
    ack: boolean;
    failedHop?: number;
    repeaters: number[];
    // (undocumented)
    type: MockZWaveFrameType.ACK;
}

// Warning: (ae-missing-release-tag) "MockZWaveFrame" is exported by the package, but it is missing a release tag (@alpha, @beta, @public, or @internal)
//
// @public
export type MockZWaveFrame = MockZWaveRequestFrame | MockZWaveAckFrame;

// Warning: (ae-missing-release-tag) "MockZWaveFrameType" is exported by the package, but it is missing a release tag (@alpha, @beta, @public, or @internal)
//
// @public (undocumented)
export enum MockZWaveFrameType {
    // (undocumented)
    ACK = 1,
    // (undocumented)
    Request = 0
}

// Warning: (ae-missing-release-tag) "MockZWaveRequestFrame" is exported by the package, but it is missing a release tag (@alpha, @beta, @public, or @internal)
//
// @public (undocumented)
export interface MockZWaveRequestFrame {
    ackRequested: boolean;
    payload: ICommandClass;
    repeaters: number[];
    // (undocumented)
    type: MockZWaveFrameType.Request;
}

// Warning: (ae-missing-release-tag) "SpyTransport" is exported by the package, but it is missing a release tag (@alpha, @beta, @public, or @internal)
//
// @public
export class SpyTransport extends Transport {
    constructor();
    // (undocumented)
    log(info: any, next: () => void): any;
    // (undocumented)
    get spy(): jest.Mock;
}

// Warnings were encountered during analysis:
//
// src/MockNode.ts:46:3 - (ae-forgotten-export) The symbol "PartialCCCapabilities" needs to be exported by the entry point index.d.ts

// (No @packageDocumentation comment for this package)

```
---
title: "Host Integration Server に付属の BizTalk アダプター |Microsoft ドキュメント"
description: "彼に含まれているアプリケーションのホスト、ホスト ファイル、DB2、および WebSphere MQ の BizTalk アダプターの概要"
author: MandiOhlinger
manager: anneta
ms.date: 10/10/2017
ms.prod: biztalk-server
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.author: mandia
ms.openlocfilehash: 26f2bf48c9a1268aace041776ff3895c8f3b3aa5
ms.sourcegitcommit: 75d35f6f230f0846c29a4b146c6d5b074e60b13c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/11/2017
---
# <a name="biztalk-adapters-for-host-systems"></a>BizTalk アダプターのホスト システム


## <a name="biztalk-adapter-for-host-applications"></a>BizTalk Adapter for ホスト アプリケーション

Microsoft BizTalk Adapter for ホスト アプリケーションは、BizTalk Server に適しています。 Windows-Initiated を処理するため、既存の IBM メインフレーム zSeries (CICS と IMS) またはミッドレンジ iSeries (RPG) サーバーのプログラムに効率的なクライアント アクセスを有効にする Microsoft トランザクション インテグレーター (TI) テクノロジに基づいています。 

TI デザイン ツールは、Visual Studio および IT 開発者はクライアント プロキシを定義するときに、高い生産性を向上して、XSD スキーマを作成する、BizTalk Server ソリューションと統合されます。 BizTalk Server 管理者のサポートを改善し、必要なリモート BizTalk Server ソリューションの展開シナリオをサポートする Microsoft 管理コンソール (MMC) スナップインで、既存の TI マネージャーが強化されました。

参照してください[ホスト アプリケーション用の BizTalk アダプター](https://msdn.microsoft.com/library/dn148497(BTS.80).aspx)です。 

## <a name="biztalk-adapter-for-host-files"></a>ホスト ファイル用の BizTalk アダプター
Microsoft BizTalk Adapter for ホスト ファイルは、IT 組織にアクセスし、メインフレーム zSeries VSAM データセットおよびミッドレンジ iSeries 物理ファイルをなど、ホスト ファイル システムに格納された情報を統合できるようにする高度なデータ アダプターです。 

Visual Studio デザイン ツールは、BizTalk アダプターの XSD としてエクスポートしているホスト プログラムで説明されているファイルのメタデータのマップを定義する、BizTalk Server ソリューション内で使用されます。 ウィザードは、BizTalk Server 管理ツールに統合されて、構成できるようにする IT プロフェッショナルは動的送信ポートと静的を定義し、送信請求応答受信ポート、簡略化された一連の SQL コマンド (SELECT、INSERT、UPDATE、DELETE に基づく). 

この BizTalk アダプターは、SQL をリレーショナルでないホスト データセットおよびメンバーにマップされるホスト ファイルの Microsoft .NET Framework データ プロバイダーに基づいています。 これにより、プログラマでない読み書きするホスト ファイル データ ソースを簡単にします。

参照してください[ホスト ファイル用の BizTalk アダプター](https://msdn.microsoft.com/library/dn150042(BTS.80).aspx)です。

## <a name="biztalk-adapter-for-db2"></a>BizTalk Adapter for DB2
Microsoft BizTalk Adapter for DB2 は、it プロフェッショナルをコンピューティング プラットフォーム、IBM メインフレーム zSeries とミッドレンジ iSeries (DB2/400)、および IBM DB2 のリモート ホスト上の IBM DB2 データベース サーバーに格納されている重要なデータにアクセスできるようにするリレーショナル データベース アダプターUniversal Database (UDB) オープン プラットフォームです。 

標準の SQL コマンドと BizTalk Server 管理ツールに組み込まれた構成ウィザードを使用して、IT プロフェッショナルは、読み取りし、データベース プログラミングすることがなく DB2 への書き込みをソリューションに作成できます。 DB2 アダプターは、Microsoft .NET Framework Data Provider for DB2 に基づいては、動的送信ポートと静的など、機能の広範な範囲のサポートおよび送信請求応答の受信ポート。

参照してください[BizTalk Adapter for DB2](https://msdn.microsoft.com/library/dn150160(BTS.80).aspx)です。

## <a name="biztalk-adapter-for-websphere-mq"></a>BizTalk Adapter for WebSphere MQ
Microsoft BizTalk Adapter for WebSphere MQ (クライアント ベース) は、リモートの MQSeries キュー マネージャーとの通信に IBM WebSphere MQ Client (クライアント ベース) と IBM WebSphere MQ 拡張トランザクションのクライアント (拡張クライアント) Api を使用します。 アダプターにより、展開および WebSphere MQ Server for Windows、効率的とメッセージを交換基幹業務を管理することがなく Windows 以外のオペレーティング システムに展開されている MQSeries キュー マネージャーと直接通信するために BizTalk Server企業全体にわたるアプリケーション。 

ベース クライアントに使用する場合、アダプターは、メッセージの配信のみを保証する非トランザクション メッセージの処理を提供します。 重複するメッセージを処理する受信側では、アプリケーションの役割です。 拡張されたクライアントに使用する場合、アダプターはトランザクション メッセージがメッセージを 1 回と-専用の 1 回だけ配信を保証するために処理を提供します。

参照してください[BizTalk Adapter for WebSphere MQ](https://msdn.microsoft.com/library/dn191830(BTS.80).aspx)です。

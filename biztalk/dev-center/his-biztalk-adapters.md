---
title: Host Integration Server に付属の BizTalk アダプター |Microsoft Docs
description: 彼に含まれるアプリケーションをホスト、ホスト ファイル、DB2、および WebSphere MQ の BizTalk アダプターの概要
author: MandiOhlinger
manager: anneta
ms.date: 10/10/2017
ms.prod: biztalk-server
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.author: mandia
ms.openlocfilehash: 138e49965520505c2f45203836af7172dfd56612
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401535"
---
# <a name="biztalk-adapters-for-host-systems"></a>BizTalk アダプターのホスト システム


## <a name="biztalk-adapter-for-host-applications"></a>ホスト アプリケーション用 BizTalk アダプター

ホスト アプリケーション用の Microsoft BizTalk Adapter は、BizTalk Server 用に設計されています。 Windows-Initiated を処理するため、既存の IBM メインフレーム zSeries (CICS と IMS) またはミッドレンジ iSeries (RPG) サーバーのプログラムへの効率的なクライアント アクセスできる Microsoft トランザクション インテグレーター (TI) テクノロジに基づいています。 

TI のデザイン ツールは、Visual Studio および BizTalk Server ソリューションを IT 開発者は、クライアント プロキシを定義するときに生産性の高いが有効にして、XSD スキーマの作成と統合されます。 BizTalk Server 管理者、サポートを改善し、必要なリモート BizTalk Server ソリューションの展開シナリオをサポートする Microsoft 管理コンソール (MMC) スナップインで、既存の TI マネージャーが強化されました。

参照してください[ホスト アプリケーション用 BizTalk アダプター](https://msdn.microsoft.com/library/dn148497(BTS.80).aspx)します。 

## <a name="biztalk-adapter-for-host-files"></a>ホスト ファイル用の BizTalk アダプター
ホスト ファイル用の Microsoft BizTalk アダプターは、IT 組織にアクセスして、メインフレーム zSeries VSAM データセットと midrange iSeries 物理ファイルを含む、ホスト ファイル システムに格納されている情報を統合できるようにする高度なデータ アダプターです。 

Visual Studio デザイン ツールは、BizTalk アダプターの XSD としてエクスポートしているホスト プログラムで説明されているファイルのメタデータのマップを定義する、BizTalk Server ソリューション内で使用されます。 ウィザードは、BizTalk Server 管理ツールに統合されて、構成、動的送信ポートと静的を定義し、応答を送信請求できるよう IT プロフェッショナルの受信ポート、簡略化された一連の SQL コマンド (SELECT、INSERT、UPDATE、DELETE に基づく). 

この BizTalk アダプターは非リレーショナルのホストのデータセットとメンバーに SQL をマップするホスト ファイル用の Microsoft .NET Framework データ プロバイダーに基づきます。 これにより、プログラマーが読み取るし、ホスト ファイル データ ソースを作成しやすくなります。

参照してください[ホスト ファイル用の BizTalk アダプター](https://msdn.microsoft.com/library/dn150042(BTS.80).aspx)します。

## <a name="biztalk-adapter-for-db2"></a>BizTalk Adapter for DB2
Microsoft BizTalk Adapter for DB2 は、it プロフェッショナルはリモート ホストのコンピューティング プラットフォーム、IBM メインフレーム zSeries と midrange iSeries (DB2/400)、および IBM DB2 の IBM DB2 データベース サーバーに格納されている重要なデータにアクセスできるようにするリレーショナル データベース アダプターUniversal Database (UDB) オープン プラットフォームです。 

IT プロフェッショナルは、標準の SQL コマンドと BizTalk Server 管理ツールに組み込まれている構成ウィザードを使用して、データベース プログラミングの必要なしに、DB2 に読み書きするソリューションを作成できます。 Microsoft .NET Framework Data Provider for DB2 に基づいては、動的送信ポート、および静的関数の広範な範囲をサポートし、応答を送信請求 DB2 アダプターの受信ポート。

参照してください[BizTalk Adapter for DB2](https://msdn.microsoft.com/library/dn150160(BTS.80).aspx)します。

## <a name="biztalk-adapter-for-websphere-mq"></a>BizTalk Adapter for WebSphere MQ
Microsoft BizTalk Adapter for WebSphere MQ (クライアント ベース) では、IBM WebSphere MQ Client (クライアント ベース) と IBM WebSphere MQ 拡張トランザクション クライアント (拡張クライアント) Api を使用してリモートの MQSeries キュー マネージャーと通信します。 アダプターにより、BizTalk Server のデプロイし、管理の WebSphere MQ サーバーの Windows を効率的に基幹業務でのメッセージを交換することがなく、非 Windows オペレーティング システムに展開されている MQSeries キュー マネージャーと直接通信するには企業全体にわたってアプリケーション。 

ベース クライアントを併用すると、アダプターはメッセージの配信のみを保証する非トランザクション メッセージの処理を提供します。 重複するメッセージを処理するために、受信側アプリケーションの役目です。 拡張クライアントと共に使用すると、アダプターはトランザクション メッセージがメッセージの 1 回、および専用の 1 回の配信を保証するために処理を提供します。

参照してください[BizTalk Adapter for WebSphere MQ](https://msdn.microsoft.com/library/dn191830(BTS.80).aspx)します。

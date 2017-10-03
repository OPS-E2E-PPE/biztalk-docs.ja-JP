---
title: "アダプター コンポーネント |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 383e8bcb-2b4d-40f9-9e98-f49e8d6f30f7
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2a5f2a78a9ea555d22f585c0aa50eda65b6c287
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="adapter-components"></a>アダプター コンポーネント
カスタム アダプターは、ネイティブ アダプターで使用される標準化された構成、管理、および設定のメカニズムを共有します。 アダプター フレームワークが標準化されているため、カスタム アダプターは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで管理されます。  
  
 次の図は、カスタム アダプターの主要なコンポーネントを示しています。 アダプターのレジストリ ファイル、アダプターのデザイン時コンポーネントとアダプターの実行時コンポーネントです。  
  
 ![](../core/media/elementsofanadapter.gif "ElementsOfAnAdapter")  
  
## <a name="adapter-registry-file"></a>アダプターのレジストリ ファイル  
 アダプターに関する特定の情報は、レジストリおよび BizTalk 管理データベースに登録する必要があります。 アダプターのエイリアス、受信ハンドラー、受信場所、トランスポートの種類などの情報はメタデータと呼ばれます。 これらのメタデータ エントリは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して手動でアダプターを登録する際に作成されます。 代わりに、カスタム アダプターのレジストリ ファイルを生成するアダプター レジストリ ウィザード (AdapterRegistryWizard.exe) の SDK ユーティリティを実行することができます。 このレジストリ ファイルをダブルクリックするかをクリックすると**インポート**上、**ファイル**] メニューの [レジストリ エディター (regedit32.exe) を使用して、メタデータをレジストリに書き込まれます。  
  
> [!NOTE]
>  このレジストリ ファイルを実行しても、アダプター情報は BizTalk 管理データベースに追加されません。 アダプター情報の追加は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して手動で行う必要があります。  
  
## <a name="design-time-component"></a>デザイン時コンポーネント  
 カスタム アダプターのユーザー インターフェイス (UI) を実装するには、アダプター フレームワークを使用します。 UI は、アダプターのアセンブリの一部として提供される XML スキーマから表示されます。したがって、この方法を使用すると UI を効率的に開発できます。 少量のコードでスキーマのコンテンツを UI に変換し、アダプターのプロパティを構成することができます。  
  
 SQL アダプターなどのアプリケーション アダプターと通信する必要があるオーケストレーションの場合は、アダプター メタデータの追加ウィザードを使用して、スキーマ、メッセージの種類、ポートの種類などのアダプター メタデータを BizTalk プロジェクトに追加できます。 アプリケーション アダプターのアダプター メタデータの追加ウィザードを使用して、対応するスキーマをシステムに組み込みます。 (非アダプター) を BizTalk プロジェクト内からこのウィザードを起動するには、プロジェクトを右クリックし、順にポイント**生成した項目の追加**、 をクリックして**アダプター メタデータの追加**およびの一覧から選択が登録されます。アダプター メタデータをインポートするアダプター。  
  
## <a name="run-time-component"></a>実行時コンポーネント  
 通常、アダプターが 2 つのパブリック実行時コンポーネントで構成されます。 メッセージの受信者と、メッセージの送信者を実装するコンポーネントを実装するコンポーネントです。 これらのコンポーネントは、同一のアセンブリまたは 2 つの異なるアセンブリに展開できます。  
  
#### <a name="receive-adapter"></a>受信アダプター  
 受信アダプターは、ネットワーク/データ ソース ストリームをメッセージ本文に添付して新しい BizTalk メッセージを作成します。 また、データの受信元エンドポイントに関するメタデータを追加して、そのメッセージをメッセージング エンジンに送信します。 アダプターは、受信エンドポイントからデータを削除したり、適切な確認メッセージをクライアントに送信して、データが [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で受理されたことを示します。  
  
#### <a name="send-adapter"></a>送信アダプター  
 送信アダプターは、特定のトランスポート プロトコルを使用して指定のエンドポイントに BizTalk メッセージを送信します。  
  
## <a name="see-also"></a>参照  
 [アダプター フレームワークとは何ですか。](../core/what-is-the-adapter-framework.md)
---
title: アダプター コンポーネント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 383e8bcb-2b4d-40f9-9e98-f49e8d6f30f7
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 215bb12537bbd0df859c59c8914c6cba63cd139a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361605"
---
# <a name="adapter-components"></a>アダプター コンポーネント
カスタム アダプターでは、標準化された構成、管理、およびネイティブ アダプターで使用される設定のメカニズムを共有します。 使用して、アダプター フレームワークが標準化、カスタム アダプターが管理されている、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
 カスタム アダプターの主要なコンポーネントを次に示します: アダプターのレジストリ ファイル、アダプターのデザイン時コンポーネントとアダプターの実行時コンポーネントです。  
  
 ![](../core/media/elementsofanadapter.gif "ElementsOfAnAdapter")  
  
## <a name="adapter-registry-file"></a>アダプターのレジストリ ファイル  
 アダプターに関する特定の情報は、レジストリおよび BizTalk 管理データベースに登録する必要があります。 アダプターのエイリアスなどの情報の受信ハンドラー、受信場所、およびトランスポートの種類はメタデータと呼ばれます。 使用して手動でアダプター登録中にこれらのメタデータ エントリが作成、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 または、カスタム アダプターのレジストリ ファイルを生成するアダプター レジストリ ウィザード (AdapterRegistryWizard.exe) の SDK ユーティリティを実行できます。 このレジストリ ファイルをダブルクリックするか、クリックして**インポート**上、**ファイル**] メニューの [レジストリ エディター (regedit32.exe) を使用して、メタデータをレジストリに書き込まれます。  
  
> [!NOTE]
>  このレジストリ ファイルを実行しても、BizTalk 管理データベースにアダプターの情報は追加されません。 使用して手動で行う必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
## <a name="design-time-component"></a>デザイン時コンポーネント  
 カスタム アダプターのユーザー インターフェイス (UI) は、アダプター フレームワークを使用して実装されます。 これは、アダプターのアセンブリの一部として提供される XML スキーマから、UI がレンダリングされるため、生産性の高い UI 開発アプローチです。 アダプターのプロパティを構成するための UI に、スキーマの内容を変換する少量のコードが必要です。  
  
 アダプター メタデータの追加ウィザードでは、SQL アダプターなどのアプリケーション アダプターと通信する必要があるオーケストレーションをスキーマ、メッセージの種類、およびポートの種類などのアダプター メタデータを BizTalk プロジェクトに追加できます。 アプリケーション アダプターと共にアダプター メタデータの追加ウィザードを使用して、システムに対応するスキーマを取得します。 (アダプター以外) を BizTalk プロジェクト内からこのウィザードを起動するには、プロジェクトを右クリックして**生成した項目の追加**、 をクリックして**アダプター メタデータの追加**と登録の一覧から選択します。アダプター メタデータをインポートするアダプター。  
  
## <a name="run-time-component"></a>実行時コンポーネント  
 通常、アダプターがパブリックの 2 つの実行時コンポーネントで構成されます。 メッセージの受信者と、メッセージの送信者を実装するコンポーネントを実装するコンポーネント。 同じアセンブリ内、または 2 つの異なるアセンブリでは、これらのコンポーネントをデプロイできます。  
  
#### <a name="receive-adapter"></a>受信アダプター  
 受信アダプターはメッセージの本文に、ネットワーク/データ ソースのストリームを添付して新しい BizTalk メッセージを作成します。 データを受信したし、をメッセージング エンジンには、そのメッセージを送信し、エンドポイントに関連するメタデータを追加します。 アダプターが、受信エンドポイントからデータを削除したりにデータが受理されたことを示すクライアントに適切な受信確認メッセージを送信[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
#### <a name="send-adapter"></a>送信アダプター  
 送信アダプターは BizTalk メッセージをその特定のトランスポート プロトコルを使用して、指定されたエンドポイントに送信するためです。  
  
## <a name="see-also"></a>参照  
 [アダプター フレームワークについて](../core/what-is-the-adapter-framework.md)
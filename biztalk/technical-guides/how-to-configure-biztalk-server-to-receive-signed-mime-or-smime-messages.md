---
title: "MIME または SMIME メッセージを受信する BizTalk Server を構成する方法が署名されて |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 50570257-7bb6-4ede-9026-873eefd06483
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88487fb96c89b8a611ab591223fa1820f70de1cd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-biztalk-server-to-receive-signed-mime-or-smime-messages"></a>MIME または SMIME メッセージを受信する BizTalk Server を構成する方法が署名済み
このトピックは、構成する方法を説明[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]符号付きの MIME/SMIME メッセージを受信する証明書を使用します。 以下の手順は、AS2 トランスポート経由での署名付きメッセージの受信の構成にも適用されます。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行する必要がありますログインする必要がのメンバーとして、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者グループ。  
  
### <a name="to-configure-biztalk-server-to-receive-signed-messages"></a>署名付きメッセージを受信する BizTalk Server を構成するには  
  
1.  次のように、署名付きメッセージを受信するためのパイプラインを作成します。  
  
    > [!NOTE]
    >  この手順に含まれるので、AS2Receive と AS2EdiReceive パイプラインを署名付きメッセージを受信の AS2 トランスポートを構成するときは必要ありません[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]この機能を提供します。  
  
    1.  受信パイプラインを作成し、受信パイプラインのデコード ステージに MIME/SMIME デコーダー パイプライン コンポーネントをドラッグします。  
  
    2.  **プロパティ**ウィンドウで、MIME/SMIME デコーダー パイプライン コンポーネントのプロパティを構成します。  
  
        > [!NOTE]
        >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して BizTalk グループにパイプラインを展開した後、受信場所のパイプライン プロパティを構成できます。 BizTalk グループの受信場所ごとに、異なるパイプライン プロパティを構成できます。  
  
    3.  受信パイプラインをビルドして配置します。  
  
2.  次のように、署名付きメッセージを受信するための受信場所を構成します。  
  
    1.  署名付きメッセージを受信する受信場所を含む BizTalk アプリケーションに、受信パイプラインを含むに作成した BizTalk アセンブリを追加します。  
  
        > [!NOTE]
        >  この手順は、AS2Receive パイプラインと AS2EdiReceive パイプラインが BizTalk EDI アプリケーションに含まれるために署名付きメッセージを受信するは、AS2 トランスポートを構成するときに必要な[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
    2.  前の手順で作成した受信パイプラインを使用して BizTalk アプリケーションで受信場所を構成します。  
  
3.  次のように、署名付きメッセージを受信するための証明書で、パーティを構成します。  
  
    -   開く、**パーティのプロパティ** ダイアログ ボックスをクリックして、BizTalk Server 管理コンソールで、**証明書** タブで、をクリックして**参照**、適切な証明書を選択クリックして**OK**です。  
  
        > [!NOTE]
        >  パーティの署名確認に使用する証明書は、他のパーティの署名確認に使用する証明書と重複しない、一意のものでなければなりません。  
  
## <a name="see-also"></a>参照  
 [MIME または SMIME メッセージの証明書の構成](../technical-guides/configuring-certificates-for-mime-or-smime-messages.md)
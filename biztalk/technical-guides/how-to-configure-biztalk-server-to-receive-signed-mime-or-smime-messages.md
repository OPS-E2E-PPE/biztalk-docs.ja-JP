---
title: MIME または SMIME メッセージに署名された受信する BizTalk Server を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 50570257-7bb6-4ede-9026-873eefd06483
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26882e196fe90d87b9e63bc13d487f60ac99627c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65253322"
---
# <a name="how-to-configure-biztalk-server-to-receive-signed-mime-or-smime-messages"></a>MIME または SMIME メッセージに署名された受信する BizTalk Server を構成する方法
このトピックでは、構成する方法を説明[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]証明書を使用して署名された MIME/SMIME メッセージを受信します。 以下の手順は、AS2 トランスポート経由での署名付きメッセージの受信の構成にも適用されます。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行する必要がありますがログオンしてのメンバーとして、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者グループ。  
  
### <a name="to-configure-biztalk-server-to-receive-signed-messages"></a>署名付きメッセージを受信する BizTalk Server を構成するには  
  
1. 次のように、署名付きメッセージを受信するためのパイプラインを作成します。  
  
   > [!NOTE]
   >  この手順に含まれるので、AS2Receive と AS2EdiReceive パイプラインを署名付きメッセージを受信するため、AS2 トランスポートを構成するときは必要ありません[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]この機能を提供します。  
  
   1. 受信パイプラインを作成し、受信パイプラインのデコード ステージに MIME/SMIME デコーダー パイプライン コンポーネントをドラッグします。  
  
   2. **プロパティ**ウィンドウで、MIME/SMIME デコーダー パイプライン コンポーネントのプロパティを構成します。  
  
      > [!NOTE]
      >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して BizTalk グループにパイプラインを展開した後、受信場所のパイプライン プロパティを構成できます。 BizTalk グループの受信場所ごとに、異なるパイプライン プロパティを構成できます。  
  
   3. 受信パイプラインをビルドして配置します。  
  
2. 次のように、署名付きメッセージを受信するための受信場所を構成します。  
  
   1. 署名付きメッセージを受信する受信場所を含む BizTalk アプリケーションに受信パイプラインを含むに作成した BizTalk アセンブリを追加します。  
  
      > [!NOTE]
      >  この手順は、AS2Receive と AS2EdiReceive パイプラインで BizTalk EDI アプリケーションに含まれるため、署名付きメッセージを受信するは、AS2 トランスポートを構成するときは必要ありません[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
   2. 前の手順で作成した受信パイプラインを備えた BizTalk アプリケーションでは、受信場所を構成します。  
  
3. 次のように、署名付きメッセージを受信するための証明書で、パーティを構成します。  
  
   -   オープン、**パーティのプロパティ** ダイアログ ボックスで、BizTalk Server 管理コンソール をクリックして、**証明書** タブで、をクリックして**参照**、適切な証明書を選択クリックして**OK**します。  
  
       > [!NOTE]
       >  パーティの署名確認に使用する証明書は、他のパーティの署名確認に使用する証明書と重複しない、一意のものでなければなりません。  
  
## <a name="see-also"></a>参照  
 [MIME またはメッセージの SMIME 証明書の構成](../technical-guides/configuring-certificates-for-mime-or-smime-messages.md)
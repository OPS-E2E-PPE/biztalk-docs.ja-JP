---
title: MIME または SMIME メッセージに署名された BizTalk Server 送信を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ba42463b-2c12-4329-919e-aca427d14eee
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e1f3e01179f26c825480bb3a7de8d13b8539129
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005467"
---
# <a name="how-to-configure-biztalk-server-to-send-signed-mime-or-smime-messages"></a>MIME または SMIME メッセージに署名された送信する BizTalk Server を構成する方法
このトピックでは、構成する方法を説明[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]証明書を使用して署名された MIME/SMIME メッセージを送信します。 以下の手順は、AS2 トランスポート経由で、署名付きメッセージの送信の構成にも適用されます。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行する必要がありますがログオンしてのメンバーとして、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者グループ。  
  
### <a name="to-configure-biztalk-server-to-send-signed-messages"></a>署名付きメッセージを送信する BizTalk Server を構成するには  
  
1. 次のように、署名付きメッセージを送信するためのパイプラインを作成します。  
  
   > [!NOTE]
   >  この手順に含まれるため、AS2Send および AS2EdiSend パイプラインを署名付きメッセージを送信するための AS2 トランスポートを構成するときは必要ありません[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]この機能を提供します。  
  
   1. 送信パイプラインを作成し、パイプラインのエンコード ステージに MIME/SMIME エンコーダー パイプライン コンポーネントをドラッグします。  
  
   2. **プロパティ**ウィンドウで、MIME/SMIME エンコーダー パイプライン コンポーネント署名の種類プロパティは、署名または [blobsign] を構成します。  
  
      > [!NOTE]
      >  暗号化を使用しても場合は、[blobsign] のみ選択できます。  
      > 
      > [!NOTE]
      >  BizTalk グループにパイプラインを展開した後、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して送信パイプライン コンポーネントのプロパティを構成できます。  
      > 
      > [!NOTE]
      >  MIME/SMIME エンコーダー パイプライン コンポーネントは、暗号化とデジタル署名の両方を実行します (両方の機能を実行するように構成されている場合)。 したがって、暗号化および署名されたメッセージを送信するように [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成する場合は、同じ送信パイプラインを使用できます。 つまり、暗号化用とデジタル署名用に異なるパイプラインを作成する必要はありません。  
  
   3. 送信パイプラインをビルドして配置します。  
  
2. 次のように、署名付きメッセージを送信するための送信ポートを構成するには。  
  
   1. 署名付きメッセージを送信する送信ポートを含む BizTalk アプリケーションに送信パイプラインを含むに作成した BizTalk アセンブリを追加します。  
  
      > [!NOTE]
      >  この手順は、AS2Send および AS2EdiSend パイプラインが BizTalk EDI アプリケーションに含まれているために、メッセージ署名を送信するための AS2 トランスポートを構成するときは必要ありません[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
   2. BizTalk アプリケーションを前の手順で作成した送信パイプラインで送信ポートを構成します。  
  
3. 次のように、署名付きメッセージを送信するための証明書で、グループを構成します。  
  
   1. [BizTalk グループを展開して、インストールした署名証明書を BizTalk グループの構成、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールの右クリックして**BizTalk グループ**、] をクリックし、 **プロパティ**します。  
  
   2. 証明書] タブをクリックし**参照**適切な証明書を選択し、[クリックして**OK**します。  
  
## <a name="see-also"></a>参照  
 [MIME またはメッセージの SMIME 証明書の構成](../technical-guides/configuring-certificates-for-mime-or-smime-messages.md)
---
title: 送信ポートから証明書を削除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send ports, certificates
- managing [send ports], certificates
- certificates, deleting
- deleting, certificates
ms.assetid: fd93a83f-c2aa-4de2-9996-4ca4ec6d4a4c
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0cee3cb77368b8128ad5be66e4628f9c693f71c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335096"
---
# <a name="how-to-remove-a-certificate-from-a-send-port"></a>送信ポートから証明書を削除する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、送信ポートからセキュリティ証明書を削除する方法を説明します。 これを行うときに、送信ポートのメッセージが暗号化されなくメッセージは、クリア テキストで送信されます。 送信ポートから証明書の削除は削除されません証明書ストアから。  
  
> [!NOTE]
>  アプリケーション開発者から削除できますセキュリティ証明書を送信ポートを開発プロセス中にこのトピックの手順を使用しています。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-remove-a-certificate-from-a-send-port"></a>送信ポートから証明書を削除するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、BizTalk グループと、送信ポートから証明書を削除する BizTalk アプリケーションを展開します。  
  
3. 展開**送信ポート**は、送信ポートを右クリックし、[**プロパティ**、] をクリックし、**証明書**します。  
  
4. クリックして**証明書の削除**、順にクリックします**OK**します。  
  
## <a name="see-also"></a>参照  
 [送信ポートの作成および構成](../core/creating-and-configuring-send-ports.md)
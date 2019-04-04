---
title: 認証を構成する方法のオプションは、受信ポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [receive ports], configuring
- authenticating, configuring
- managing [receive ports], authenticating
- receive ports, configuring
- configuring, authenticating
- configuring, receive ports
- authenticating, receive ports
ms.assetid: ce213ef0-ae91-47cf-84bf-0f86cc684bce
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52ca3f5d4636f0592c98528d481a8d3f0a1bc96b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001779"
---
# <a name="how-to-configure-authentication-options-for-a-receive-port"></a>受信ポートの認証オプションを構成する方法
このトピックでは、BizTalk Server 管理コンソールを使用して受信ポートのメッセージ認証オプションを構成する方法について説明します。 メッセージ認証オプションは、パーティの解決の認証が構成されると適用されます。 使用可能なオプションは次のとおりです。  
  
- **認証はありません。** このオプションを選択すると、受信ポートはメッセージの資格情報を確認せずにメッセージを渡します。  
  
- **認証が失敗した場合は、メッセージを削除します。** このオプションを選択すると、受信ポートはパーティの解決を使用してメッセージの資格情報をチェックし、認証に失敗した場合はメッセージを破棄します。  
  
- **認証が失敗した場合は、メッセージを保持します。** : このオプションを選択すると、受信ポートはパーティの解決を使用してメッセージの資格情報をチェックし、認証に失敗した場合はメッセージを保留キューに保持します。  
  
  手順の作成とパーティの構成については、[パーティを作成する方法](http://msdn.microsoft.com/library/f6feca1d-bc83-4fb6-981d-26c9e0d53044)を参照してください。 パーティの解決の認証の詳細については、[メッセージの送信者の認証](../core/authenticating-the-sender-of-a-message.md)と[受信メッセージの認証](../core/inbound-message-authentication.md)を参照してください。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-configure-authentication-options-for-a-receive-port"></a>受信ポートの認証オプションを構成するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、BizTalk グループを展開し、受信ポートの認証を構成する BizTalk アプリケーションを展開します。  
  
3. クリックして**受信ポート**受信ポートを右クリックし、クリックして**プロパティ**します。  
  
4. **認証**セクションで、選択し、をクリックし、 **OK**します。  
  
## <a name="see-also"></a>参照  
 [受信ポートの管理](../core/managing-receive-ports.md)
---
title: 受信マップを構成する方法、受信ポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [receive ports], configuring
- configuring, maps
- configuring, inbound maps
- maps, configuring
- receive ports, configuring
- receive ports, inbound maps
- configuring, receive ports
- maps, inbound
- managing [receive ports], inbound maps
ms.assetid: b7448b39-f024-4353-818b-f753c2d60751
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5624d81597648b84d576fddc74909aff5b1742a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341450"
---
# <a name="how-to-configure-inbound-maps-for-a-receive-port"></a>受信ポートの受信マップを構成する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、受信ポートの受信マップを構成する方法について説明します。 受信マップを使用すると、受信メッセージのスキーマを別のスキーマに変換できます。たとえば、パートナーから受信したメッセージを、自社で使用されているスキーマに変換することが可能となります。  
  
 マップを使用すると、オーケストレーションでメッセージを処理することなく、受信ポートによって送信されたメッセージに XSL 変換を適用できます。 受信マップの追加、マップの削除、既存のマップから別のマップへの変更を行うことができます。 受信ポートに 1 つ以上のマップを追加することができますが、各マップには、一意の送信元スキーマが必要です。 します。 マップの背景については、次を参照してください。[マップ](../core/maps.md)します。  
  
> [!NOTE]
>  アプリケーション開発者が開発プロセス中に受信ポート用のマップを構成するには、このトピックの手順を実行します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-configure-inbound-maps-for-a-receive-port"></a>受信ポートの受信マップを構成するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、BizTalk グループを展開し、受信ポートの受信マップを構成する BizTalk アプリケーションを展開します。  
  
3. クリックして**受信ポート**は、受信ポートを右クリックし、**プロパティ**、順にクリックします**受信マップ**します。  
  
4. 次の表で説明されているように、受信マップを構成し、 **OK**します。  
  
   |プロパティ|目的|  
   |--------------|----------------|  
   |**[削除]**|選択したマップを削除する場合にクリックします。|  
   |**ソース ドキュメント**|ドロップダウン リストから、このポートで使用する送信元スキーマを選択します。|  
   |**マップ**|ドロップダウン リストから、このポートに関連付けるマップを選択します。|  
   |**送信先ドキュメント**|ドロップダウン リストから、このポートで使用する送信先スキーマを選択します。|  
  
## <a name="see-also"></a>参照  
 [受信ポートの管理](../core/managing-receive-ports.md)   
 [マップの管理](../core/managing-maps.md)
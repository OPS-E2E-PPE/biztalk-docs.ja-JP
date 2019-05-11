---
title: 送信マップを構成する方法、受信ポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [receive ports], configuring
- maps, outbound
- configuring, maps
- managing [receive ports], outbound maps
- maps, configuring
- receive ports, configuring
- configuring, receive ports
- receive ports, outbound maps
ms.assetid: 01a864a1-9e8c-4b82-9d03-91be09d556da
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee2d18a2a1d0e8d39001a232d909a805a27f4707
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341282"
---
# <a name="how-to-configure-outbound-maps-for-a-receive-port"></a>受信ポートの送信マップを構成する方法
このトピックでは、BizTalk Server 管理コンソールを使用して受信ポートの送信マップを構成する方法について説明します。 要求 - 応答の受信ポートと共に送信マップを使用すると、送信メッセージのスキーマを別のスキーマに変換できます。たとえば、会社が使用するメッセージを取引先が使用するスキーマに変換できます。  
  
 マップを使用すると、オーケストレーションでメッセージを処理することなく、受信ポートによって送信された応答メッセージに XSL 変換を適用できます。 出力マップの追加、マップの削除、既存のマップから別のマップへの変更を行うことができます。 受信ポートに 1 つ以上のマップを追加することができますが、各マップには、一意の送信元スキーマが必要です。 します。 マップの背景については、次を参照してください。[マップ](../core/maps.md)します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-configure-outbound-maps-for-a-receive-port"></a>受信ポートの送信マップを構成するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、BizTalk グループを展開し、受信ポートの送信マップを構成する BizTalk アプリケーションを展開します。  
  
3. 展開**受信ポート**は、受信ポートを右クリックし、[**プロパティ**、] をクリックし、**送信マップ**します。  
  
4. 次の表に示すように、送信マップを構成し、 **OK**します。  
  
   |プロパティ|目的|  
   |--------------|----------------|  
   |**[削除]**|選択したマップを削除する場合にクリックします。|  
   |**ソース ドキュメント**|ドロップダウン リストから、このポートで使用する送信元スキーマを選択します。|  
   |**マップ**|ドロップダウン リストから、このポートに関連付けるマップを選択します。|  
   |**送信先ドキュメント**|ドロップダウン リストから、このポートで使用する送信先スキーマを選択します。|  
  
## <a name="see-also"></a>参照  
 [受信ポートの管理](../core/managing-receive-ports.md)   
 [マップの管理](../core/managing-maps.md)
---
title: "送信マップを構成する方法、受信ポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9006f655879bcb5d8fe2c2448c8feba0642c9a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-outbound-maps-for-a-receive-port"></a>受信ポートの送信マップを構成する方法
このトピックでは、BizTalk Server 管理コンソールを使用して受信ポートの送信マップを構成する方法について説明します。 要求 - 応答の受信ポートと共に送信マップを使用すると、送信メッセージのスキーマを別のスキーマに変換できます。たとえば、会社が使用するメッセージを取引先が使用するスキーマに変換できます。  
  
 マップを使用すると、オーケストレーションでメッセージを処理することなく、受信ポートによって送信された応答メッセージに XSL 変換を適用できます。 出力マップの追加、マップの削除、既存のマップから別のマップへの変更を行うことができます。 受信ポートに複数のマップを追加することができますが、各マップには、一意の送信元スキーマが必要です。 マップに関する背景情報については、次を参照してください。[マップ](../core/maps.md)です。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
### <a name="to-configure-outbound-maps-for-a-receive-port"></a>受信ポートの送信マップを構成するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、受信ポートの送信マップを構成する BizTalk アプリケーションを展開します。  
  
3.  展開**受信ポート**受信ポートを右クリックしをクリックして**プロパティ**、順にクリック**送信マップ**です。  
  
4.  次の表の説明に従って、送信マップを構成し、をクリックして**OK**です。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**[削除]**|選択したマップを削除する場合にクリックします。|  
    |**ソース ドキュメント**|ドロップダウン リストから、このポートで使用する送信元スキーマを選択します。|  
    |**マップ**|ドロップダウン リストから、このポートに関連付けるマップを選択します。|  
    |**対象のドキュメント**|ドロップダウン リストから、このポートで使用する送信先スキーマを選択します。|  
  
## <a name="see-also"></a>参照  
 [受信ポートの管理](../core/managing-receive-ports.md)   
 [マップを管理します。](../core/managing-maps.md)
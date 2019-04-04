---
title: 送信ポートの受信マップを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [send ports], inbound maps
- configuring, send ports
- send ports, inbound maps
- configuring, inbound maps
- managing [send ports], configuring
- send ports, configuring
ms.assetid: 213c66ba-928f-4c00-9a87-f45eaa9f7dca
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5afe1edd63f10f39619948fb69d657bbaf85b81
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996107"
---
# <a name="how-to-configure-inbound-maps-for-a-send-port"></a>送信ポートの受信マップを構成する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、送信ポートの受信マップを構成する方法について説明します。 受信マップは、動的または静的な送信請求 - 応答の送信ポートでのみ使用されます。 マップを使用すると、オーケストレーションでメッセージを処理することなく、ポートが受け取った応答メッセージに XSL 変換を適用できます。 受信マップの追加、マップの削除、既存のマップから別のマップへの変更を行うことができます。 送信ポートには複数のマップを追加できます。ただし、各マップには一意の送信元スキーマが必要となります。 マップの背景については、[マップ](../core/maps.md)を参照してください。  
  
> [!NOTE]
>  アプリケーション開発者が開発プロセス中にマップを構成するには、このトピックの手順を実行します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-configure-inbound-maps-for-a-send-port"></a>送信ポートの受信マップを構成するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、BizTalk グループを展開し、送信ポートの受信マップを構成する BizTalk アプリケーションを展開します。  
  
3. 展開**送信ポート**は、送信ポートを右クリックし、[**プロパティ**、] をクリックし、**受信マップ**します。  
  
4. 次の表で説明されているように、受信マップを構成し、 **OK**します。 複数のマップを追加または削除する場合は、この手順を必要に応じて繰り返します。  
  
   |プロパティ|目的|  
   |--------------|----------------|  
   |**[削除]**|選択したマップを削除する場合にクリックします。|  
   |**ソース ドキュメント**|ドロップダウン リストから、受信マップの送信元ドキュメントを選択します。|  
   |**マップ**|ドロップダウン リストから、送信元ドキュメントと送信先ドキュメントに関連付けられているマップを選択します。|  
   |**送信先ドキュメント**|ドロップダウン リストから、受信マップの送信先ドキュメントを選択します。|  
  
## <a name="see-also"></a>参照  
 [作成と送信ポートの構成](../core/creating-and-configuring-send-ports.md)   
 [マップの管理](../core/managing-maps.md)
---
title: 送信ポートの受信マップを構成する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 04179476795e7b7c224b3db1b5e83c8a87f68b72
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248466"
---
# <a name="how-to-configure-inbound-maps-for-a-send-port"></a>送信ポートの受信マップを構成する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、送信ポートの受信マップを構成する方法について説明します。 受信マップは、動的または静的な送信請求 - 応答の送信ポートでのみ使用されます。 マップを使用すると、オーケストレーションでメッセージを処理することなく、ポートが受け取った応答メッセージに XSL 変換を適用できます。 受信マップの追加、マップの削除、既存のマップから別のマップへの変更を行うことができます。 送信ポートには複数のマップを追加できます。ただし、各マップには一意の送信元スキーマが必要となります。 マップに関する背景情報については、次を参照してください。[マップ](../core/maps.md)です。  
  
> [!NOTE]
>  アプリケーション開発者が開発プロセス中にマップを構成するには、このトピックの手順を実行します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
### <a name="to-configure-inbound-maps-for-a-send-port"></a>送信ポートの受信マップを構成するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、送信ポートの受信マップを構成する BizTalk アプリケーションを展開します。  
  
3.  展開**送信ポート**、送信ポートを右クリックし、をクリックして**プロパティ**、クリックして**受信マップ**です。  
  
4.  次の表に示すように、受信マップを構成し、をクリックして**OK**です。 複数のマップを追加または削除する場合は、この手順を必要に応じて繰り返します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**[削除]**|選択したマップを削除する場合にクリックします。|  
    |**ソース ドキュメント**|ドロップダウン リストから、受信マップの送信元ドキュメントを選択します。|  
    |**マップ**|ドロップダウン リストから、送信元ドキュメントと送信先ドキュメントに関連付けられているマップを選択します。|  
    |**対象のドキュメント**|ドロップダウン リストから、受信マップの送信先ドキュメントを選択します。|  
  
## <a name="see-also"></a>参照  
 [作成して、送信ポートの構成](../core/creating-and-configuring-send-ports.md)   
 [マップを管理します。](../core/managing-maps.md)
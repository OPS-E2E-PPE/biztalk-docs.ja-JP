---
title: 送信ポートの送信マップを構成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, outbound maps
- configuring, send ports
- managing [send ports], configuring
- send ports, outbound maps
- send ports, configuring
- managing [send ports], outbound maps
ms.assetid: 9f5f5504-5a7f-4b21-9a65-91dce9d35890
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51d3feaba929d1a7585a8e7c3b29f6868dcc9dc7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248090"
---
# <a name="how-to-configure-outbound-maps-for-a-send-port"></a>送信ポートの送信マップを構成する方法
ここでは、BizTalk Server 管理コンソールを使って、送信ポートの送信マップを構成する方法について説明します。 マップを使用すると、オーケストレーションでメッセージを処理することなく、送信ポートによって送信されたメッセージに XSL 変換を適用できます。 出力マップの追加、マップの削除、既存のマップから別のマップへの変更を行うことができます。 送信ポートには複数のマップを追加できます。ただし、各マップには一意の送信元スキーマが必要となります。 マップに関する背景情報については、次を参照してください。[マップ](../core/maps.md)です。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
### <a name="to-configure-outbound-maps-for-a-send-port"></a>送信ポートに対して送信マップを構成するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、送信ポートの送信マップを構成する BizTalk アプリケーションを展開します。  
  
3.  展開**送信ポート**、送信ポートを右クリックし、をクリックして**プロパティ**、クリックして**送信マップ**です。  
  
4.  次の表の説明に従って、送信マップを構成し、をクリックして**OK**です。 複数のマップを追加または削除する場合は、この手順を必要に応じて繰り返します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**[削除]**|選択したマップを削除する場合にクリックします。|  
    |**送信マップ-ソース ドキュメント**|ドロップダウン リストから、送信マップの送信元ドキュメントを選択します。|  
    |**送信マップ-マップ**|ドロップダウン リストから、送信元ドキュメントと送信先ドキュメントに関連付けられているマップを選択します。|  
    |**送信マップ-送信先ドキュメント**|ドロップダウン リストから、送信マップの送信先ドキュメントを選択します。|  
  
## <a name="see-also"></a>参照  
 [作成して、送信ポートの構成](../core/creating-and-configuring-send-ports.md)   
 [マップを管理します。](../core/managing-maps.md)
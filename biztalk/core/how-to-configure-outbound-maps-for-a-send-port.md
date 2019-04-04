---
title: 送信ポートの送信マップを構成する方法 |Microsoft Docs
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
ms.openlocfilehash: d1dc02d2936cad6fd24ee944e3c27c64831bc65f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023184"
---
# <a name="how-to-configure-outbound-maps-for-a-send-port"></a>送信ポートの送信マップを構成する方法
ここでは、BizTalk Server 管理コンソールを使って、送信ポートの送信マップを構成する方法について説明します。 マップを使用すると、オーケストレーションでメッセージを処理することなく、送信ポートによって送信されたメッセージに XSL 変換を適用できます。 出力マップの追加、マップの削除、既存のマップから別のマップへの変更を行うことができます。 送信ポートには複数のマップを追加できます。ただし、各マップには一意の送信元スキーマが必要となります。 マップの背景については、[マップ](../core/maps.md)を参照してください。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-configure-outbound-maps-for-a-send-port"></a>送信ポートに対して送信マップを構成するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、BizTalk グループを展開し、送信ポートの送信マップを構成する BizTalk アプリケーションを展開します。  
  
3. 展開**送信ポート**は、送信ポートを右クリックし、[**プロパティ**、] をクリックし、**送信マップ**します。  
  
4. 次の表に示すように、送信マップを構成し、 **OK**します。 複数のマップを追加または削除する場合は、この手順を必要に応じて繰り返します。  
  
   |プロパティ|目的|  
   |--------------|----------------|  
   |**[削除]**|選択したマップを削除する場合にクリックします。|  
   |**送信マップ-ソース ドキュメント**|ドロップダウン リストから、送信マップの送信元ドキュメントを選択します。|  
   |**送信マップ-マップ**|ドロップダウン リストから、送信元ドキュメントと送信先ドキュメントに関連付けられているマップを選択します。|  
   |**送信マップ]-[送信先ドキュメント**|ドロップダウン リストから、送信マップの送信先ドキュメントを選択します。|  
  
## <a name="see-also"></a>参照  
 [作成と送信ポートの構成](../core/creating-and-configuring-send-ports.md)   
 [マップの管理](../core/managing-maps.md)
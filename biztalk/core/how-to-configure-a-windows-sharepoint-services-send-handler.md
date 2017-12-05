---
title: "サービスの送信ハンドラーを Windows SharePoint を構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring [Windows SharePoint Services adapters], send handlers
- send handlers, Windows SharePoint Services adapters
- Windows SharePoint Services adapters, send handlers
ms.assetid: 457767d9-6e39-4553-9bbe-212fcb7c04bc
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8e110fb2a671fc839fb96cfdc2ad03169649e6e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-configure-a-windows-sharepoint-services-send-handler"></a>Windows SharePoint Services 送信ハンドラを構成する方法
次の手順を使用して、Windows SharePoint Services 送信ハンドラが関連付けられているホストを変更します。  
  
> [!NOTE]
>  各ホストに関連付けられる送信ハンドラーは 1 つだけです。  
  
### <a name="to-change-global-variables-for-a-windows-sharepoint-services-send-handler"></a>Windows SharePoint Services 送信ハンドラのグローバル変数を変更するには  
  
1.  BizTalk Server 管理コンソールをクリックして展開[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**、クリックして展開し、 **BizTalk グループ [\<servername\>:\<管理データベース\>]**をクリックして展開**プラットフォームの設定**、クリックして展開し、**アダプター**です。 フォルダの下にアダプタの一覧が表示されます。  
  
2.  をクリックして**Windows SharePoint Services**、右側のウィンドウで、構成、およびをクリックする送信ハンドラを右クリックし、**プロパティ**です。  
  
3.  **アダプター ハンドラーのプロパティ** ダイアログ ボックスで、**全般** タブの 、**ホスト名**一覧で、送信ハンドラーが関連付けられる、ホストを選択します。  
  
4.  **全般** タブで、をクリックして**プロパティ**です。  
  
5.  **Windows SharePoint Services トランスポート プロパティ** ダイアログ ボックスで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[送信バッチ サイズ]|Windows SharePoint Services の Web サービスがバッチとして処理するドキュメントの最大数を指定します。 既定値は 20 です。 **注:**最小値は 1 です。|  
  
## <a name="see-also"></a>参照  
 [サービスの受信場所を Windows SharePoint を構成する方法](../core/how-to-configure-a-windows-sharepoint-services-receive-location.md)   
 [Windows SharePoint Services 送信ポートを構成する方法](../core/how-to-configure-a-windows-sharepoint-services-send-port.md)   
 [送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)   
 [Windows SharePoint Services アダプターのプロパティのリファレンス](../core/windows-sharepoint-services-adapter-properties-reference.md)   
 [Windows SharePoint Services アダプターの式](../core/windows-sharepoint-services-adapter-expressions.md)   
 [サポートされている Windows SharePoint Services 列の型](../core/supported-windows-sharepoint-services-column-types.md)
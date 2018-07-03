---
title: サービスの送信ハンドラーを Windows SharePoint を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [Windows SharePoint Services adapters], send handlers
- send handlers, Windows SharePoint Services adapters
- Windows SharePoint Services adapters, send handlers
ms.assetid: 457767d9-6e39-4553-9bbe-212fcb7c04bc
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90ac23759558549122f31a793852b479b67744d4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988555"
---
# <a name="how-to-configure-a-windows-sharepoint-services-send-handler"></a>Windows SharePoint Services 送信ハンドラを構成する方法
次の手順を使用して、Windows SharePoint Services 送信ハンドラが関連付けられているホストを変更します。  
  
> [!NOTE]
>  各ホストに関連付けられる送信ハンドラーは 1 つだけです。  
  
### <a name="to-change-global-variables-for-a-windows-sharepoint-services-send-handler"></a>Windows SharePoint Services 送信ハンドラのグローバル変数を変更するには  
  
1. BizTalk Server 管理コンソールで、クリックして展開[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**をクリックして展開と**BizTalk グループ [\<servername\>:\<管理データベース\>]** をクリックして展開**プラットフォームの設定**をクリックして展開と**アダプター**します。 フォルダの下にアダプタの一覧が表示されます。  
  
2. クリックして**Windows SharePoint Services**、右側のウィンドウで、構成、およびクリックする送信ハンドラーを右クリック**プロパティ**します。  
  
3. **アダプター ハンドラーのプロパティ** ダイアログ ボックスの 、**全般** タブで、**ホスト名**一覧で、送信ハンドラーが関連付けられているが、ホストを選択します。  
  
4. **全般**] タブで [**プロパティ**します。  
  
5. **Windows SharePoint Services トランスポート プロパティ** ダイアログ ボックスで、次の操作を行います。  
  
   |プロパティ|目的|  
   |--------------|----------------|  
   |[送信バッチ サイズ]|Windows SharePoint Services の Web サービスがバッチとして処理するドキュメントの最大数を指定します。 既定値は 20 です。 **注:** 最小値は 1 です。|  
  
## <a name="see-also"></a>参照  
 [サービスの受信場所を Windows SharePoint を構成する方法](../core/how-to-configure-a-windows-sharepoint-services-receive-location.md)   
 [Windows SharePoint Services 送信ポートを構成する方法](../core/how-to-configure-a-windows-sharepoint-services-send-port.md)   
 [送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)   
 [Windows SharePoint Services アダプターのプロパティに関するリファレンス](../core/windows-sharepoint-services-adapter-properties-reference.md)   
 [Windows SharePoint Services アダプターの式](../core/windows-sharepoint-services-adapter-expressions.md)   
 [サポートされている Windows SharePoint Services 列の型](../core/supported-windows-sharepoint-services-column-types.md)
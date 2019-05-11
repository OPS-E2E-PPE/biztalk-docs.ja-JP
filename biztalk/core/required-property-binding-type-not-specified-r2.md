---
title: 必須のプロパティ バインド種類が指定されていません (R2) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c8e45783-6454-44e2-867e-e30092725f51
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e959b7e3e0a48dea0d18a73a898d2c39bfd576e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65267597"
---
# <a name="required-property-binding-type-not-specified-r2"></a>必要なプロパティのバインドの種類が指定されていません (R2)
## <a name="details"></a>詳細  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  製品名   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 製品バージョン |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    イベント ID     |                                         0                                          |
|  イベント ソース   |                                         0                                          |
|    コンポーネント    |                                         0                                          |
|  シンボル名  |                                         0                                          |
|  メッセージ テキスト   |                    必要なプロパティが指定されていないバインドの種類                    |
  
## <a name="explanation"></a>説明  
 Wcf-custom または Wcf-customisolated トランスポートを構成するときに、バインドの種類プロパティは設定されませんでした。  
  
## <a name="user-action"></a>ユーザーの操作  
 バインドの種類のプロパティを構成するのにには、次の手順を使用します。  
  
#### <a name="to-configure-the-binding-type-property"></a>バインドの種類のプロパティを構成するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。  
  
2. コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。  
  
3. アプリケーションを見つけて、トランスポートを特定します。  
  
4. トランスポート名を右クリックします。  
  
5. **[プロパティ]** をクリックします。  
  
6. ポート**型**一覧で、適切なポートを選択します。  
  
7. をクリックして**構成**です。  
  
8. **WCF--[**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブ。  
  
9. 値を指定、**バインドの種類**一覧。  
  
   バインディングの構成の詳細については、次のリソースを参照してください。  
  
-   [Wcf-customisolated 受信場所を構成する方法](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [Wcf-custom 受信場所を構成する方法](../core/how-to-configure-a-wcf-custom-receive-location.md)  
  
-   [Wcf-custom 送信ポートを構成する方法](../core/how-to-configure-a-wcf-custom-send-port.md)
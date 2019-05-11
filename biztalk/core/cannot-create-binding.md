---
title: バインディングを作成することはできません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fbe1bd54-6031-4f90-a445-c1647b382a1a
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7910cf4c6e16d5af75e49bb829f1418a5e1455c
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528213"
---
# <a name="cannot-create-binding"></a>バインドを作成できません
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                               |
| 製品バージョン |                                           [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                           |
|    イベント ID     |                                                                       0                                                                        |
|  イベント ソース   |                                                                       0                                                                        |
|    コンポーネント    |                                                                       0                                                                        |
|  シンボル名  |                                                                       0                                                                        |
|  メッセージ テキスト   | バインドの種類が指定されていないために、バインドを作成することはできません。 "BasicHttpBinding"、"wsHttpBinding"または"customBinding のようなバインドの種類を指定します。 |
  
## <a name="explanation"></a>説明  
 BindingType プロパティを Wcf-custom または Wcf-customisolated トランスポートを構成した後、コードで設定されませんでした。 または、他のコード パスで問題になります。 値は、バインド設定のユーザー インターフェイスが必要です。 構成を確認し、受信場所のプロパティ 領域で、ドロップダウン リストからバインドの種類が選択されていることを確認します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、Wcf-custom または Wcf-customisolated トランスポートを構成するコードを確認します。 いることを確認、 **BindingType**プロパティの XML データで、 **TransportTypeData** ITransportInfo インターフェイスのプロパティが適切に設定します。  
  
 また、ようにバインドの種類を指定**basicHttpBinding**、 **wsHttpBinding**、または**customBinding**します。  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。  
  
2. コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。  
  
3. アプリケーションを見つけて、トランスポートを特定します。  
  
4. トランスポート名を右クリックします。  
  
5. **[プロパティ]** をクリックします。  
  
6. ポート**型**一覧で、適切なポートを選択します。  
  
7. をクリックして**構成**です。  
  
8. **WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブ。  
  
9. 値が指定されていることを確認、**バインドの種類**一覧。  
  
   バインディングの構成の詳細については、の次のリソースを参照してください、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。  
  
-   [Wcf-customisolated 受信場所を構成する方法](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [Wcf-custom 受信場所を構成する方法](../core/how-to-configure-a-wcf-custom-receive-location.md)  
  
-   [Wcf-custom 送信ポートを構成する方法](../core/how-to-configure-a-wcf-custom-send-port.md)
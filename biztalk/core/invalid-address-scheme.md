---
title: "無効なアドレス スキーム |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b059289-654e-40d6-a092-2a685e6e10f7
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 385f3aca555f18599887897f6b60144070f252a2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-address-scheme"></a>アドレス スキームが無効です
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|イベント ID|000|  
|イベント ソース|0|  
|コンポーネント|0|  
|シンボル名|0|  
|メッセージ テキスト|アドレス スキームが無効です。"{0}" スキームが必要です。|  
  
## <a name="explanation"></a>説明  
 トランスポート バインディングに定義されている種類と一致しないプロトコル スキームを指定しました。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** 、 をクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ルートで  **BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開と**アプリケーション**です。  
  
3.  アプリケーションを特定し、次にトランスポートを特定します。  
  
4.  トランスポート名を右クリックします。  
  
5.  **[プロパティ]**をクリックします。  
  
6.  ポート**型**一覧で、適切なポートを選択します。  
  
7.  をクリックして**構成**です。  
  
8.  **WCF [***トランスポートの種類***] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブです。  
  
9. **アドレス (URI)**テキスト ボックスに、アドレスの値が使用されている WCF アダプターの種類と一致していることを確認します。  
  
 また、システム指定のバインディングの種類で、Wcf-custom アダプターを使用する場合の値を確認、**バインドの種類**ボックスの一覧、**バインディング**タブです。場合、**バインドの種類**するように構成**customBinding**、アドレスがで表示されているトランスポート バインド要素と一致する必要があります、**バインドの種類**リストで、 **バインド**タブです。
---
title: "アドレスが無効です (絶対 uri) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5db292ad-9105-492d-a6c5-a7108159901a
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af2cb19c793bdcd7ab4a1dc18eb0ea1c98a991ed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-address-absolute-uri"></a>アドレスが無効です (絶対 URI)
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|イベント ID|0|  
|イベント ソース|0|  
|コンポーネント|0|  
|シンボル名|0|  
|メッセージ テキスト|アドレスが無効です。"{0}" は正しい形式の絶対 URI ではありません。|  
  
## <a name="explanation"></a>説明  
 このエラー イベントは、インプロセスの WCF トランスポートに整形式の絶対アドレスを指定しなかったことを示します。 たとえば、インプロセスの WCF トランスポートのアドレス プロパティには、/path/service.svc などの相対アドレスを設定できません。  
  
## <a name="user-action"></a>ユーザーの操作  
 インプロセスの WCF トランスポートのアドレスを整形式の絶対アドレスに変更します。  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** 、 をクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ルートで  **BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開と**アプリケーション**です。  
  
3.  アプリケーションを特定し、次にトランスポートを特定します。  
  
4.  トランスポート名を右クリックします。  
  
5.  **[プロパティ]**をクリックします。  
  
6.  ポート**型**一覧で、適切なポートを選択します。  
  
7.  をクリックして**構成**です。  
  
8.  **WCF [***トランスポートの種類***] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブです。  
  
9. **アドレス (URI)**テキスト ボックス。 アドレスを変更します。 整形式の絶対アドレスの一例は http://localhost/path/service.svc です。
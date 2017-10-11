---
title: "アドレスが無効です (相対 uri) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a953f3e-3768-4e61-8f25-ea958a5a701a
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 101a4544a83eb02438478d6d526dba422c44ae7b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-address-relative-uri"></a>アドレスが無効です (相対 URI)
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
 正しい形式の相対アドレスを使用して WCF 分離受信場所が指定されていませんでした。 たとえば、http://localhost/svc は相対アドレスとして使用できません。 WCF 分離受信場所の "アドレス" プロパティを絶対アドレスに設定することはできません。  
  
## <a name="user-action"></a>ユーザーの操作  
 受信場所のアドレスを構成するには、次の手順を実行します。  
  
#### <a name="to-configure-the-receive-location-address"></a>受信場所のアドレスを構成するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** 、 をクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ルートで  **BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開と**アプリケーション**です。  
  
3.  アプリケーションと、検索をトランスポートを特定します。  
  
4.  トランスポート名を右クリックします。  
  
5.  **[プロパティ]**をクリックします。  
  
6.  ポート**型**一覧で、適切なポートを選択します。  
  
7.  をクリックして**構成**です。  
  
8.  **WCF [***トランスポートの種類***] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブです。  
  
9. **アドレス (URI)**テキスト ボックスで、スラッシュ (「/」) で開始するように、アドレスを変更します。  
  
 受信場所の詳細については、次の情報を参照してください。  
  
-   [Wcf-customisolated 受信場所を構成する方法](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [Wcf-wshttp 受信場所を構成する方法](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [Wcf-basichttp 受信場所を構成する方法](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)
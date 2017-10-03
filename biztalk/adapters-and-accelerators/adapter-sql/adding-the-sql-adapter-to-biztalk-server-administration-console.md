---
title: "BizTalk Server 管理コンソールへの SQL アダプタの追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fd974f28-c9cb-46de-95be-83716231ebcd
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3510fb31bffe4c5823593fac34d5d5f1d5849c65
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="adding-the-sql-adapter-to-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールへの SQL アダプタの追加
[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で BizTalk WCF カスタム ポートまたは WCF SQL ポートとして使用できます。 使用する場合、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] WCF カスタム ポートを経由は WCF カスタム ポートを追加する必要はありません、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールに、WCF カスタム ポートが追加されるため、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]既定では管理コンソールです。 ただし、使用する場合、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] WCF-SQL ポートを介して、WCF-SQL アダプターを追加する必要があります最初、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
 このトピックは、WCF SQL アダプターを追加する方法を示します、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
> [!IMPORTANT]
>  これらの手順に従う場合は、WCF カスタム ポートを構成する必要はありません、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
## <a name="add-the-sql-adapter"></a>SQL アダプタを追加します。  
  
1.  開く、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
2.  展開して、 **BizTalk グループ**、展開**プラットフォームの設定**、し、**アダプター**です。  
  
3.  右クリック**アダプター**、 をポイント**新規**を選択して**アダプター**です。  
  
     ![アダプタの追加](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")  
  
4.  **アダプター プロパティ**] ダイアログ ボックスで、アダプターとの間の名前を入力、**アダプター**一覧で、[ **WCF-SQL**です。  
  
     ![WCF &#45; を追加します。Biztalk SQL アダプター](../../adapters-and-accelerators/adapter-sql/media/4c6e2650-5d3a-4de8-a60a-a136d93a6fcf.gif "4c6e2650-5d3a-4de8-a60a-a136d93a6fcf")  
  
5.  [ **OK**] を選択します。  
  
## <a name="see-also"></a>参照  
 [SQL アダプタを BizTalk アプリケーションを開発する構成要素](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)
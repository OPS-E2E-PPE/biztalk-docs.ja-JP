---
title: BizTalk Server 管理コンソールへの SQL アダプタの追加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd974f28-c9cb-46de-95be-83716231ebcd
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff3eb1aa8870316ec506a61658c34db6acc7f62c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005731"
---
# <a name="adding-the-sql-adapter-to-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールへの SQL アダプタの追加
[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] Biztalk WCF カスタム ポートまたは WCF SQL ポートとして使用できます。 使用する場合、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] WCF カスタム ポートには WCF カスタム ポートを追加する必要はありません、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールに、WCF カスタム ポートが追加されるため、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]既定では、管理コンソール。 ただし、使用する場合、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] WCF SQL ポートを経由する WCF-SQL アダプターを最初に追加する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
 このトピックでは、WCF-SQL アダプターを追加する方法、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
> [!IMPORTANT]
>  WCF カスタム ポートを構成する場合は、これらの手順を実行する必要はありません、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  
  
## <a name="add-the-sql-adapter"></a>SQL アダプタを追加します。  
  
1. 開く、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
2. 展開、 **BizTalk グループ**、展開**プラットフォームの設定**、し、**アダプター**します。  
  
3. 右クリック**アダプター**、 をポイント**新規**、選択と**アダプター**します。  
  
    ![アダプターを追加する](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")  
  
4. **アダプター プロパティ**] ダイアログ ボックスに、アダプターの場合との間の名前を入力、**アダプター**一覧で、[ **WCF-SQL**します。  
  
    ![WCF の追加&#45;biztalk SQL アダプター](../../adapters-and-accelerators/adapter-sql/media/4c6e2650-5d3a-4de8-a60a-a136d93a6fcf.gif "4c6e2650-5d3a-4de8-a60a-a136d93a6fcf")  
  
5. **[OK]** を選択します。  
  
## <a name="see-also"></a>参照  
 [SQL アダプターを使用した BizTalk アプリケーションを開発する構成要素](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)
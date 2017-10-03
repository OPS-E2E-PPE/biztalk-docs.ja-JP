---
title: "BizTalk グループ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Management database, groups
- groups
- groups, Management database
- groups, about groups
ms.assetid: 197cbcf6-c722-4cbb-9642-3cb8a34757e2
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b9cd38012f0e2a7ba5f4cfcb56ae63678aacbf8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="biztalk-groups"></a>BizTalk グループ

## <a name="overview"></a>概要
*BizTalk グループ*を通常、企業、部署、ハブ、または、BizTalk Server の実装を必要とするその他のビジネス単位を表す組織の単位です。 BizTalk グループは、BizTalk Server 管理データベース ([!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では BizTalk Server 構成データベースと呼ばれている) と一対一の関係にあります。  
  
> [!NOTE]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] グループは複数の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターを含むことができますが、ある特定の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターは、1 つの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] グループのみと関連付けることができます。  
  
 BizTalk 管理データベースには、BizTalk グループとそのグループ内の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターの構成情報が格納されています。 この構成情報には、サーバーのメッセージ処理ロジックの一部とこのロジックを物理的に実行する場所が指定されます。 BizTalk Server 管理データベースの詳細については、次を参照してください。 [BizTalk Server でのデータベース](../core/databases-in-biztalk-server.md)です。  
  
 グループ内の各サーバーのインストールに同じ BizTalk Server 管理データベースを指定する必要があります。これにより、管理コンソールから各サーバーを管理できます。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server の構成](../install-and-config-guides/configure-biztalk-server.md)   
 [グループを管理します。](../core/managing-groups.md)   
 [エンティティ](../core/entities.md)
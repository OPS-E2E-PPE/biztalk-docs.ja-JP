---
title: BizTalk グループ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Management database, groups
- groups
- groups, Management database
- groups, about groups
ms.assetid: 197cbcf6-c722-4cbb-9642-3cb8a34757e2
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 960f7afa1138e1be3293ae3bc0c65898539630d8
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528301"
---
# <a name="biztalk-groups"></a>BizTalk グループ

## <a name="overview"></a>概要
*BizTalk グループ*は通常、企業、部署、ハブ、または含まれている BizTalk Server の実装を必要とするその他の部署を表す組織の単位です。 BizTalk グループが BizTalk Server 管理データベースと一対一のリレーションシップ (で BizTalk Server 構成データベースと呼ばれる[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)])。  
  
> [!NOTE]
>  中に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループが複数あります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、特定のコンピューター、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューターが 1 つに関連付けることのみ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ。  
  
 BizTalk 管理データベースは、BizTalk グループの構成情報を格納し、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ内のコンピューター。 この構成情報には、サーバーと、このロジックを物理的に実行するためのメッセージ処理ロジックの一部を指定します。 BizTalk Server 管理データベースの詳細については、次を参照してください。 [BizTalk Server でのデータベース](../core/databases-in-biztalk-server.md)します。  
  
 管理コンソールから、各サーバーを管理できるように、グループのサーバーのインストールごとに同じ BizTalk Server 管理データベースを指定する必要があります。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server の構成](../install-and-config-guides/configure-biztalk-server.md)   
 [グループの管理](../core/managing-groups.md)   
 [エンティティ](../core/entities.md)
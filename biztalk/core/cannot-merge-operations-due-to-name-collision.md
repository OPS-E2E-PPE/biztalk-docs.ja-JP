---
title: 名前の競合のための操作を結合できません |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 81ddb8b7-6f7e-420c-b7c3-921c0e305326
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8f884b4eea6be64f1d1575b157805703d12cee3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231714"
---
# <a name="cannot-merge-operations-due-to-name-collision"></a>名前が競合しているため、操作を結合できません
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|イベント ID|0|  
|イベント ソース|0|  
|コンポーネント|0|  
|シンボル名|0|  
|メッセージ テキスト|名前が競合しているため、操作 "{0}" を結合できません。 Web サービスの操作の名前はすべて一意である必要があります。|  
  
## <a name="explanation"></a>説明  
 このエラーは、結合対象の 2 つのポートのポート名または操作名が同じであることを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 ポート構成ウィザードを使用して、結合対象のすべてのポートが異なるポート名と操作名であることを確認します。  
  
 ポート構成の詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプで次の情報を参照してください。  
  
-   [ポート構成ウィザードを実行する方法](../core/how-to-run-the-port-configuration-wizard.md)
---
title: 名前の競合のため、操作をマージすることはできません |Microsoft Docs
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
ms.openlocfilehash: a8ab241fe80b63f833c9eb373627d445dc7fd08d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357627"
---
# <a name="cannot-merge-operations-due-to-name-collision"></a>名前が競合しているため、操作を結合できません
## <a name="details"></a>詳細  
  
|                 |                                                                                                             |
|-----------------|-------------------------------------------------------------------------------------------------------------|
|  製品名   |             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]              |
| 製品バージョン |                         [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                          |
|    イベント ID     |                                                      0                                                      |
|  イベント ソース   |                                                      0                                                      |
|    コンポーネント    |                                                      0                                                      |
|  シンボル名  |                                                      0                                                      |
|  メッセージ テキスト   | 操作を結合できません"{0}"名前の競合が原因です。 Web サービスの操作の名前はすべて一意である必要があります。 |
  
## <a name="explanation"></a>説明  
 このエラーは、結合対象の 2 つのポートのポート名または操作名が同じであることを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 ポート構成ウィザードを使用して、結合対象のすべてのポートが異なるポート名と操作名であることを確認します。  
  
 ポート構成の詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプで次の情報を参照してください。  
  
-   [ポート構成ウィザードを実行する方法](../core/how-to-run-the-port-configuration-wizard.md)
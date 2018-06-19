---
title: プロジェクトの場所が空でない |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: db353050-3662-4ab6-8898-4e4d3bd78ac1
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2de1e1dd381a75f596b4980430ddcc5d6d8982b6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278786"
---
# <a name="the-project-location-is-not-empty"></a>プロジェクトの場所は空ではありません
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|イベント ID|0|  
|イベント ソース|0|  
|コンポーネント|0|  
|シンボル名|0|  
|メッセージ テキスト|プロジェクトの場所 "{0}" は空ではありません。 次のいずれかを実行する必要があります: 1。 新しいプロジェクトを 2 に別の場所を選択します。 指定して、既存の場所または 3 を再利用する場合は上書きされます。 プロジェクトの場所の内容を手動で削除します。|  
  
## <a name="explanation"></a>説明  
 このエラーは、サービスを公開する予定の仮想ディレクトリが空ではないことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 同じ場所を再利用するには、上書きの場所を選択します。 または、新しい場所を指定します。  WCF サービス公開ウィザードで選択**既存の場所を上書き** をクリック**次**です。 この手順で、場所が上書きされます。
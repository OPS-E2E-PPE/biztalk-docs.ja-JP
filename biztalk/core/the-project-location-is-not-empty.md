---
title: プロジェクトの場所が空でない |Microsoft Docs
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
ms.openlocfilehash: 5fc106b534973f13544b9bafa85f190d8ed2c255
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994291"
---
# <a name="the-project-location-is-not-empty"></a>プロジェクトの場所は空ではありません
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                                 |
| 製品バージョン |                                                                                             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                                                             |
|    イベント ID     |                                                                                                                         0                                                                                                                          |
|  イベント ソース   |                                                                                                                         0                                                                                                                          |
|    コンポーネント    |                                                                                                                         0                                                                                                                          |
|  シンボル名  |                                                                                                                         0                                                                                                                          |
|  メッセージ テキスト   | プロジェクトの場所"{0}"が空でないです。 次のいずれかを実行する必要があります: 1。 新しいプロジェクトに、2 の別の場所を選択します。 指定、既存の場所または 3 を再利用する場合は上書きします。 プロジェクトの場所の内容を手動で削除します。 |
  
## <a name="explanation"></a>説明  
 このエラーは、サービスを公開する予定の仮想ディレクトリが空ではないことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 同じ場所を再利用するには、上書きの場所を選択します。 または、新しい場所を指定します。  WCF サービス公開ウィザードで選択**既存の場所を上書き** をクリック**次**します。 この手順で、場所が上書きされます。
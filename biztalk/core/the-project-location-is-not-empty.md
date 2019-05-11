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
ms.openlocfilehash: 6fd44cc0d9bfefb67b96558808e6b98a46c8afc2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394087"
---
# <a name="the-project-location-is-not-empty"></a>プロジェクトの場所が空でないです。
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                                 |
| 製品バージョン |                                                                                             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                                                             |
|    イベント ID     |                                                                                                                         0                                                                                                                          |
|  イベント ソース   |                                                                                                                         0                                                                                                                          |
|    コンポーネント    |                                                                                                                         0                                                                                                                          |
|  シンボル名  |                                                                                                                         0                                                                                                                          |
|  メッセージ テキスト   | プロジェクトの場所"{0}"が空でないです。 次のいずれかを実行する必要があります。1. 新しいプロジェクトに、2 の別の場所を選択します。 指定、既存の場所または 3 を再利用する場合は上書きします。 プロジェクトの場所の内容を手動で削除します。 |
  
## <a name="explanation"></a>説明  
 このエラーを示します、仮想サービスの発行先ディレクトリが空ではありません。  
  
## <a name="user-action"></a>ユーザーの操作  
 同じ場所を再利用する上書きの場所を選択します。 または、新しい場所を指定します。  WCF サービス公開ウィザードで選択**既存の場所を上書き** をクリック**次**します。 この手順では、場所を上書きします。
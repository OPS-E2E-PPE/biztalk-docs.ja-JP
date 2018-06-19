---
title: このインスタンスがパートナーの [Batching Service] ウィンドウの範囲外 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e420d75-11fd-4221-9d97-814ca6e48c81
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e93e7e769a8f0e30b3753af690a69c5e6eaa9786
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278666"
---
# <a name="this-instance-is-outside-the-batching-service-window-for-the-partner"></a>このインスタンスはパートナーの [Batching Service] ウィンドウ内にありません
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|バッチ処理エンジン|  
|シンボル名|OutsideBatchingServiceWindow|  
|メッセージ テキスト|このインスタンスはパートナーの [Batching Service] ウィンドウ内にありません|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、バッチ処理オーケストレーションのインスタンスがパーティのアクティベーションの範囲外であったため、インスタンスを開始できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、パーティの [EDI のプロパティ] の [インターチェンジのバッチ作成用の設定] ページを開き、オーケストレーション インスタンスがアクティベーションの範囲内にあることを確認します。 以外の場合、開始時刻 プロパティを変更し、クリックして**開始**です。
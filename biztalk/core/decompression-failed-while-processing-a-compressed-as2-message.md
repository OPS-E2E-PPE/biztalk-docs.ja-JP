---
title: "圧縮された AS2 メッセージの処理中に圧縮解除が失敗しました。 | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5246ee97-cc60-4878-9447-de870c0f4c34
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4121fc3598913f4c3edab52655866c02b5a4fe86
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="decompression-failed-while-processing-a-compressed-as2-message"></a>圧縮された AS2 メッセージの処理中に圧縮解除が失敗しました。
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|AS2 エンジン|  
|シンボル名|-|  
|メッセージ テキスト|圧縮された AS2 メッセージの処理中に圧縮解除が失敗しました。 エラー: {0}|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、受信パイプラインの AS2 デコーダー コンポーネントが AS2 メッセージの圧縮を解除できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次のいずれかの操作を行います。  
  
-   AS2 メッセージの圧縮ラッパーが有効であることを確認します。  
  
-   BizTalk Server に対して圧縮解除が有効になっていることを確認します。そのためには、[AS2 のプロパティ] ダイアログ ボックスの [パーティ - AS2 メッセージの送信者] ページで [メッセージを圧縮する] プロパティがオンになっていることを確認します。  
  
-   エラー メッセージ テキストに示されるエラーの説明を参照して、具体的な問題を特定してください。
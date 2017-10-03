---
title: "フィールドの区切り記号の前後のセグメント タグ id が見つかりません |。Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5f6f0a74-3560-4d6d-9893-85e8426e6b17
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 818a061cd723c0d8f8c58570c9e6df94a670942b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="field-separator-not-found-after-segment-tag-id"></a>セグメント タグ ID の後にフィールドの区切り記号が見つかりません
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|X12SeFsNotFoundAfterTagIdDescription|  
|メッセージ テキスト|セグメント タグ ID の後にフィールドの区切り記号が見つかりません|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、インターチェンジに含まれているセグメントでセグメント識別子が使用されており、その直後にデータ要素区切り記号が続いていなかったため、受信パイプラインでインターチェンジを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、インターチェンジのすべてのセグメント識別子の直後にデータ要素区切り記号が続いていることを確認し、インターチェンジを再送信してもらいます。
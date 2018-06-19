---
title: AS2 メッセージをデコードしようとするときに BTS MIME エラーが発生しました |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65cb5ece-78e4-4b83-b126-4d8c588b2c61
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 096696f4420150cdd53f8fe561460d243c1bb018
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005075"
---
# <a name="a-bts-mime-error-was-encountered-when-attempting-to-decode-an-as2-message"></a>AS2 メッセージをデコードしようとしたときに BTS MIME エラーが発生しました
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|BizTalk Server EDI|  
|コンポーネント|AS2 エンジン|  
|シンボル名|-|  
|メッセージ テキスト|AS2 メッセージをデコードしようとしたときに BTS MIME エラーが発生しました。  AS2-から: {0}、AS2-を: {1}、MessageId: {2}、エラー: {3}|  
  
## <a name="explanation"></a>説明  
 このエラーが発生するのは、BizTalk MIME コンポーネントを使用して MIME 処理の一部を実行するときです。  
  
## <a name="user-action"></a>ユーザーの操作  
 完全なエラー メッセージは、MIME コンポーネントで発生した問題に関する情報を提供します。 (これは、AS2 コンポーネントは MIME 処理の一部の BizTalk MIME コンポーネントを使用するため)、問題の診断に BTS MIME エラー情報を参照してください。
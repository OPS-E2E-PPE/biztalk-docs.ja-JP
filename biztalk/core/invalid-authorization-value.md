---
title: 無効な認証値 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 70d0dd75-b045-4b67-ba23-78551493f074
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4e83d35e379babeedca783fa8eb00774ccf05ea
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256994"
---
# <a name="invalid-authorization-value"></a>認証の値が無効です
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|X12Ta1InvalidAuthorizationValueDescription|  
|メッセージ テキスト|認証の値が無効です|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、ISA02 の [認証情報] の値が、スキーマ (X12_AN) で指定されたデータ型に準拠していなかったか、またはスキーマ (10) で必要な桁数がなかったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。 スキーマは、BaseArtifacts.dll 内の X12ServiceSchema です。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、ISA02 ヘッダーの値が X12:AN データ型に準拠し、末尾のスペースを含めて 10 桁であることを確認してから、インターチェンジを再送信してもらいます。
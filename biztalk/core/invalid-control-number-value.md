---
title: 無効な制御番号の値 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ac762e2-2d48-45e8-b4c4-2df246b7568c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ce9df9724d85a3b4a2d6ebf28f94e4b9c05db05
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257226"
---
# <a name="invalid-control-number-value"></a>制御番号の値が無効です
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|X12Ta1InvalidControlNumberValueDescription|  
|メッセージ テキスト|制御番号の値が無効です|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、インターチェンジの制御番号の値 (インターチェンジ、グループ、またはトランザクション セット) が、スキーマで指定されたデータ型または正しい桁数に準拠していなかったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。 スキーマは、BaseArtifacts.dll 内の X12ServiceSchema または EdifactServiceSchema です。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、スキーマで定義されたデータ型および桁数に制御番号が準拠していることを確認してから、インターチェンジを再送信してもらいます。
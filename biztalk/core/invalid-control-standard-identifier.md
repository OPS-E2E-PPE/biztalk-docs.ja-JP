---
title: 無効な制御標準識別子 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d2b5a54-7f29-49c9-8bcf-a5b4b6d07ad3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94975e63d5781200ee1bfd9d14896c1e5fe722a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257018"
---
# <a name="invalid-control-standard-identifier"></a>制御標準識別子が無効です
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|X12Ta1InvalidControlStandardIdentifierDescription|  
|メッセージ テキスト|制御標準識別子が無効です|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、インターチェンジ内のインターチェンジ制御標準識別子 (フィールド ISA11) が、スキーマで指定されている列挙のエントリと一致しなかったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。 スキーマは、BaseArtifacts.dll 内の X12ServiceSchema または EdifactServiceSchema です。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、インターチェンジで使用されているインターチェンジ制御標準識別子が ISA11 フィールドの列挙のエントリと一致していることを確認し、インターチェンジを再送信してもらいます。
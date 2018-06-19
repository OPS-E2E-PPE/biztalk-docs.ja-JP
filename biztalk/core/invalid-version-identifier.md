---
title: 無効なバージョンの識別子 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 504b0b16-7d23-45ef-ae2a-ce1962b83f34
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47e1035ad6a8cf6ebae7ebde5981898a9cfce667
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22261938"
---
# <a name="invalid-version-identifier"></a>バージョン識別子が無効です
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|X12Ta1InvalidVersionIdentifierDescription|  
|メッセージ テキスト|バージョン識別子が無効です|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、インターチェンジのバージョン識別子 (X12 インターチェンジの GS08 フィールドまたは EDIFACT インターチェンジの UNG7 フィールド) が、サービス スキーマ (BaseArtifacts.dll の X12ServiceSchema または EdifactServiceSchema) によって設定されたデータ型と桁数に準拠していなかったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。 GS08 フィールドは、X12_AN データ型で、1 ～ 12 桁である必要があります。 UNG7.1 のバージョンは、EDIFACT_AN データ型で、1 ～ 3 桁である必要があります。 UNG7.2 のリリースは、EDIFACT_AN データ型で、1 ～ 3 桁である必要があります。 UNG7.3 の関連付けの割り当てコードは、EDIFACT_AN データ型で、1 ～ 6 桁である必要があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、GS08 または UNG7 のバージョンがサービス スキーマで指定されたデータ型と桁数に準拠することを確認してから、インターチェンジを再度送信します。
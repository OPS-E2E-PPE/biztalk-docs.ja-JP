---
title: 無効な合成要素区切り記号 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 738a1107-86e6-4475-a61d-ed1d9ab7e5d2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4abf047a61dc8b8f2eb89e436594e47e6f4cb067
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257258"
---
# <a name="invalid-component-element-separator"></a>コンポーネント要素区切り記号が無効です。
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|X12Ta1InvalidComponentElementSeparatorDescription\|  
|メッセージ テキスト|コンポーネント要素区切り記号が無効です。|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、インターチェンジ内のコンポーネントの区切り記号の値が ASCII 文字セット内の文字に制限されていなかったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。 X12 では、セグメント終端記号は ISA16 フィールドです。 EDIFACT では、セグメント終端記号は UNA1 フィールドです。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、セグメントの区切り記号 (X12 インターチェンジの ISA16 フィールド、または EDIFACT インターチェンジの UNA1 フィールド) が、ASCII 文字セットの文字に制限されていることを確認します。 インターチェンジを再送信します。
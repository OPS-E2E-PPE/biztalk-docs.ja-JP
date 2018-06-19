---
title: インスタンスの生成中に発生したエラーは、フィールドを繰り返すことができますが、繰り返し区切り記号が定義されていません |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c7a6783c-cb35-4ce8-9164-ec34ae500de1
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 366caec69fd84b91cf815a58e4975e8e5d7b4d06
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22290106"
---
# <a name="error-encountered-during-instance-generation--field-can-repeat-but-repetition-delimiter-has-not-been-defined"></a>インスタンスの生成中にエラーが発生しました。フィールドを繰り返すことはできますが、繰り返し区切り記号が定義されていません
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|-|  
|メッセージ テキスト|インスタンスの生成中にエラーが発生しました。 フィールド {0} を繰り返すことはできますが、繰り返し区切り記号が定義されていません。|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、スキーマの指定どおり、表示されたフィールドを繰り返すことができますが、繰り返し区切り記号が定義されていないため、BizTalk Server が X12 メッセージ インスタンスを生成できなかったことを示します。 このイベントは、スキーマのフィールドに 1 を超えるのと同等な minOccurs が設定されているが、繰り返し区切り記号ではなく、標準識別子が定義されている場合に発生します  (EDIFACT インターチェンジの場合、既定で繰り返し区切り記号が定義されます)。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、インターチェンジ受信者のパーティの [ISA セグメントの定義] ページの ISA11 で、標準識別子ではなく繰り返し区切り記号を選択し、区切り記号の文字を入力します。 インターチェンジにパーティが解決されていない場合は、グローバル プロパティの [ISA セグメントの定義] ページで繰り返し区切り記号を定義します (X12 インターチェンジの場合)。
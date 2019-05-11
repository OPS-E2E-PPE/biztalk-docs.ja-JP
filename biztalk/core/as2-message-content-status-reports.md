---
title: AS2 メッセージのコンテンツの状態レポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6244aa59-a80d-450b-ab95-9a5e14c0c40e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89504de79279a42d14061606a31985bed0563635
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358916"
---
# <a name="as2-message-content-status-reports"></a>AS2 メッセージ コンテンツのステータス レポート

## <a name="overview"></a>概要
これらの状態レポートでは、AS2 メッセージまたは MDN のヘッダーとペイロード、コンテキスト プロパティを表示します。 これには次の 3 つの AS2 メッセージ コンテンツのステータスのレポートがあります。  
  
- メッセージのワイヤ形式のレポート  
  
- メッセージのデコードされた形式のレポート  
  
- Mdn メッセージ レポート  
  
  AS2/MDN の状態レポート内で AS2 メッセージを右クリックし、をクリックしてこれらのレポートのいずれかを表示する**ビュー メッセージのワイヤ形式**、**ビュー メッセージのデコードされた形式**、または**ビュー Mdnメッセージ**します。 MDN コマンドにより、相関関係に MDN が AS2 メッセージに表示されます。  
  
  これらのレポートの各機能は、選択した、対応する「否認不可データベースにストア メッセージ」プロパティ [パーティ-AS2 メッセージの送信者] ページまたは [パーティ AS2 のプロパティ] ダイアログ ボックスの [AS2 メッセージの受信者] ページとして、関連するパーティの場合にのみ使用できます。 コマンドは、ワイヤ形式またはデコードされた形式で BizTalkDTADb データベースで AS2 メッセージまたは Mdn を格納します。  
  
  このレポートを使用して、**メッセージの詳細プロパティ ダイアログ ボックス**(UI の詳細を参照してください。 [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]) ページに分割の情報メッセージのデータを表示します。  
  
|ページ|表示されるデータ|  
|----------|--------------------|  
|**全般**|概要については、メッセージ|  
|**コンテキスト**|このメッセージに関連付けられたコンテキスト プロパティ|  
|**メッセージ部分**|このメッセージ内に含まれる個々 のドキュメント ペイロード。 各ドキュメントは、テキストまたはバイナリのいずれかとして表示できます。<br /><br /> テキスト形式のビューは、EDI テキスト ファイルなど、人間が判読できる形式で AS2 メッセージまたは MDN の内容を示しています。 AS2 ヘッダー、EDI トレーラー、および個別の行には、各セグメントの EDI ペイロードを表示します。<br />-バイナリ形式のビューは、区切りなしテキスト形式と、AS2 メッセージまたは MDN の場合は、各 ASCII 文字の 16 進数表記の表に、AS2 メッセージまたは MDN の内容を示しています。|
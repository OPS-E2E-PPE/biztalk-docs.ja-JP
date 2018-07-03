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
ms.openlocfilehash: 3f8461e2433f9d7cfb14dd0d4961704ec624db8a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996891"
---
# <a name="as2-message-content-status-reports"></a>AS2 メッセージ コンテンツの状態レポート

## <a name="overview"></a>概要
これらの状態レポートには、AS2 メッセージまたは MDN のコンテキスト プロパティ、ヘッダー、およびペイロードが表示されます。 AS2 メッセージ コンテンツの状態レポートには、次の 3 つがあります。  
  
- メッセージのワイヤ形式のレポート  
  
- メッセージのデコードされた形式のレポート  
  
- MDN メッセージ レポート  
  
  AS2/MDN の状態レポート内で AS2 メッセージを右クリックし、をクリックしてこれらのレポートのいずれかを表示する**ビュー メッセージのワイヤ形式**、**ビュー メッセージのデコードされた形式**、または**ビュー Mdnメッセージ**します。 MDN コマンドを実行すると、AS2 メッセージに関連付けられている MDN が表示されます。  
  
  各レポートを使用できるのは、関連するパーティの [AS2 のプロパティ] ダイアログ ボックスの [パーティ - AS2 メッセージの受信者] ページまたは [パーティ - AS2 メッセージの受信者] ページで、対応するプロパティ (否認不可データベースへのメッセージの保管を表す) をオンにした場合のみです。 コマンドを実行すると、AS2 メッセージまたは MDN は、ワイヤ形式またはデコードされた形式で BizTalkDTADb データベースに保存されます。  
  
  このレポートを使用して、**メッセージの詳細プロパティ ダイアログ ボックス**(UI の詳細を参照してください。 [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]) ページに分割の情報メッセージのデータを表示します。  
  
|ページ|表示されるデータ|  
|----------|--------------------|  
|**全般**|メッセージの概要|  
|**コンテキスト**|このメッセージに関連するコンテキスト プロパティ|  
|**メッセージ部分**|このメッセージ内に含まれる個別のドキュメント ペイロード。 各ドキュメントはテキストまたはバイナリとして表示できます。<br /><br /> テキスト形式のビューは、EDI テキスト ファイルなど、人間が判読できる形式で AS2 メッセージまたは MDN の内容を示しています。 このビューでは、AS2 ヘッダー、EDI トレーラー、および EDI ペイロードが表示されます。各セグメントは別々の行に表示されます。<br />-バイナリ形式のビューは、区切りなしテキスト形式と、AS2 メッセージまたは MDN の場合は、各 ASCII 文字の 16 進数表記の表に、AS2 メッセージまたは MDN の内容を示しています。|
---
title: プロパティの値が有効な文字列 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 78df6aca-26b5-4d49-93b0-71de19f5c9dd
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac165b36f741afa2a876efcf0c3e0ece22beb4f6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969811"
---
# <a name="the-property-value-is-not-a-valid-string"></a>プロパティ値が有効な文字列ではありません
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                    バッチ処理エンジン                                     |
|  シンボル名  |                                  InvalidPropertyValue                                  |
|  メッセージ テキスト   |                        プロパティ値が有効な文字列ではありません                        |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、必要なプロパティが文字列値であるが、入力された値が文字列値ではなかったため、[バッチ フィルター] ダイアログ ボックスの行のプロパティとして入力された値が無効なことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、[EDI のプロパティ] ダイアログ ボックスの [インターチェンジ バッチ作成用の設定] ページで [バッチ フィルター] ダイアログ ボックスを開きます。 文字列プロパティに入力された値が文字列であることを確認します。
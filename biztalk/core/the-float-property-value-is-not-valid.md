---
title: Float プロパティの値が無効です |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 79327dc6-fc5e-4290-9663-16bb64970d4b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d7f0752a05b9e692a002c80332032337230decb9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975075"
---
# <a name="the-float-property-value-is-not-valid"></a>浮動小数点型プロパティの値が無効です
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                    バッチ処理エンジン                                     |
|  シンボル名  |                               InvalidFloatPropertyValue                                |
|  メッセージ テキスト   |                         浮動小数点型プロパティの値が無効です                          |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、必要なプロパティが浮動小数点値であるが、入力された値が浮動小数点値ではなかったため、[バッチ フィルター] ダイアログ ボックスの行のプロパティとして入力された値が無効なことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、[EDI のプロパティ] ダイアログ ボックスの [インターチェンジ バッチ作成用の設定] ページで [バッチ フィルター] ダイアログ ボックスを開きます。 浮動小数点値である必要があるプロパティとして入力された値が、実際に浮動小数点値であることを確認します。
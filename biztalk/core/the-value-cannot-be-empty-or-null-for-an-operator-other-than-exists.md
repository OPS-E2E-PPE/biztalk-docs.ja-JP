---
title: 値が空または Exists 以外の演算子を null にすることはできません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 44de42c8-eab7-4b13-b55a-d33eabe75c52
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da58cdbb1ba351d5f9500587facc99026a503176
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977331"
---
# <a name="the-value-cannot-be-empty-or-null-for-an-operator-other-than-exists"></a>Exists 以外の演算子の値は空または Null にできません
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                    バッチ処理エンジン                                     |
|  シンボル名  |                                ValueCannotBeNullOrEmpty                                |
|  メッセージ テキスト   |          Exists 以外の演算子の値は空または Null にできません           |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、[バッチ フィルター] ダイアログ ボックスのプロパティ行に入力された値が無効であったことを示します。演算子が Exists ではないにもかかわらず、入力された値が空または Null でした。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、[EDI のプロパティ] ダイアログ ボックスの [インターチェンジ バッチ作成用の設定] ページで [バッチ フィルター] ダイアログ ボックスを開きます。 行の演算子が Exists ではない場合は、入力した値が空または Null のいずれでもないことを確認してください。
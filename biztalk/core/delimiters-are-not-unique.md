---
title: 区切り記号が一意ではありません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1c37cc55-8923-4124-9004-91ee5093df9c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed635103026d71902ab9c1f93d1849fbeff3d1c0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389680"
---
# <a name="delimiters-are-not-unique"></a>区切り記号が一意ではありません
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                                           -                                            |
|  メッセージ テキスト   |                               区切り記号が一意ではありません                                |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、インターチェンジで識別されてインターチェンジのファセットを区切るために使用されている区切り記号のうち、複数が同じ記号であったため、EDI 送信パイプラインで送信インターチェンジを処理できなかったことを示します。 区切り記号は、X12 インターチェンジの ISA セグメントと EDIFACT インターチェンジの UNA セグメントで識別されます。 同じ値を持つ複数の区切り記号は、保存されたバッチ シナリオで発生することがあります。または、インターチェンジがパススルー送信を経由して受信され、その後、送信ポートによって MessageBox で XML ファイルとして取得される場合に、発生することがあります。 このエラー状態が発生すると、インターチェンジの処理は失敗します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、インターチェンジのどの区切り記号が同じ値を持っているかを特定し、いずれかの区切り記号の値を変更します。
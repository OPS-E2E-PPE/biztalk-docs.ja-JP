---
title: セグメントのコンポーネントまたはサブコンポーネント レベルに末尾の区切り記号が |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 517f1cfc-66c1-47e6-be94-2c76c1f89230
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94b95e45cc4c6676bdbd2e787661a73547f45148
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024243"
---
# <a name="segment-has-trailing-delimiters-at-component-or-sub-component-level"></a>セグメントの末尾の区切り記号がコンポーネントまたはサブコンポーネント レベルにあります
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                      X12SeSegmentHasTrailingDelimiterDescription                       |
|  メッセージ テキスト   |         セグメントの末尾の区切り記号がコンポーネントまたはサブコンポーネント レベルにあります          |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、インターチェンジに末尾の区切り記号が含まれており、インターチェンジの受信者としてのパーティに対して末尾の区切り記号が有効化されていなかったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次のようにして末尾の区切り記号を有効化します。  
  
1.  BizTalk Server 管理コンソールを開き、[パーティ] フォルダーに移動して、パーティの [EDI のプロパティ] を開きます。  
  
2.  X12 または EDIFACT (該当する方) の検証と確認の生成のページに移動します。  
  
3.  [末尾の区切り記号を許可する] をクリックします。
---
title: 見つからない CLR Namespace および rootName のスキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: db283d81-1cb0-460d-ace4-49a91ceb4a02
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f4a854357a8f1e217273c1a3380a446dcbe7848
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396924"
---
# <a name="schema-not-found-for-clr-namespace-and-rootname"></a>見つからない CLR Namespace および rootName のスキーマ
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                               SchemaNotFoundForCLRAndRN                                |
|  メッセージ テキスト   |              スキーマが見つかりません CLR Namespace ={0}および rootName = {1}               |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、受信パイプラインが、インターチェンジに関連付けられたルート名およびインターチェンジに対して解決されたパーティに関連付けられている名前空間を使用して、ドキュメント スキーマを見つけられなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、インターチェンジから取得されたルート名と名前空間が解決されるパーティのプロパティから決定が展開されたスキーマにまとめて対応することを確認します。 BizTalk は、ドキュメントの種類と、インターチェンジ内のバージョンからルート名を決定します。 BizTalk は、(既定のスキーマ) 用の既定のターゲット Namespace フィールドまたはインターチェンジ処理のプロパティで (カスタム スキーマ用)"を有効にするカスタム トランザクション セットの定義 グリッドからスキーマを決定します。
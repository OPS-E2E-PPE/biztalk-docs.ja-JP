---
title: "CLR Namespace および rootName が見つかりませんスキーマ |。Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: db283d81-1cb0-460d-ace4-49a91ceb4a02
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06db4a89803b8386ccbb45372b72423e83c6ff7c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="schema-not-found-for-clr-namespace-and-rootname"></a>CLR Namespace および rootName のスキーマが見つかりません
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|SchemaNotFoundForCLRAndRN|  
|メッセージ テキスト|スキーマが見つかりません CLR Namespace = {0} および rootName {1} を =|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、受信パイプラインが、インターチェンジに関連付けられたルート名およびインターチェンジに解決されたパーティに関連付けられた名前空間を使用して、ドキュメント スキーマを見つけられなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、インターチェンジから取得されたルート名および解決されたパーティのプロパティから決定された名前空間が、展開されているスキーマに対応することを確認します。 BizTalk は、インターチェンジのドキュメントの種類とバージョンからルート名を特定します。 また、インターチェンジ処理のプロパティの [既定のターゲットの名前空間] フィールド (既定のスキーマの場合) または [カスタム トランザクション セットの定義を有効にします] グリッド (カスタム スキーマの場合) からスキーマを特定します。
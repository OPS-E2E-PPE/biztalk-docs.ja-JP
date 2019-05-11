---
title: スキーマの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 20b88194-b400-4ebc-8882-d493fbf30e0f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4e3197dee20a222be35aa2e72dc4ac5e04208da
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389881"
---
# <a name="creating-schemas"></a>スキーマの作成
BizTalk エディターを使用して、2 つの種類のスキーマを作成することができます。 メッセージのスキーマとプロパティ スキーマです。  
  
> [!NOTE]
>  いくつかの種類のメッセージ スキーマ、XML メッセージ スキーマやフラット ファイル メッセージ スキーマをエンベロープ スキーマなどがあります。  
  
 メッセージ スキーマでは、構造を定義しに送信し、取引先パートナーまたはアプリケーションから受信するメッセージの内容を制限します。 メッセージ スキーマは、最も一般的な種類の Microsoft で使用するスキーマ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ビジネス ドキュメントと、それを格納するために使用するエンベロープの両方の XML メッセージ スキーマを作成し、フラット ファイル メッセージ スキーマ、ヘッダー、ボディ、およびトレーラーのスキーマを含むフラット ファイル拡張子 BizTalk エディターを使用して作成できます。  
  
 プロパティ スキーマは、特殊な種類のスキーマです。 プロパティ スキーマは、フィールドやレコード データは、インスタンス メッセージ内にメッセージ コンテキストと呼ばれるものから昇格を検証テンプレートを提供します。 プロパティ スキーマでは、実行時に昇格するデータの正式な厳密に型指定された定義を指定します。  
  
 プロパティの昇格の重要な情報を取得するための一元的なメカニズムを提供します。 定義したからインスタンス メッセージより簡単にアクセスできるようにする BizTalk Server コンポーネントをメッセージの処理 BizTalk に渡されますサーバー。 昇格させたプロパティの 1 つの一般的な用途は、メッセージを処理するため正しくルーティングできるように、サブスクリプションにメッセージ インスタンスと一致します。  
  
 このセクションでは、さまざまな種類の BizTalk Server 内のスキーマを作成する方法について説明し、関連項目に関連する複数の種類のスキーマを示します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [プロジェクト内のスキーマの管理](../core/managing-schemas-within-projects.md)  
  
-   [スキーマ内のノードの管理](../core/managing-the-nodes-within-a-schema.md)  
  
-   [プロパティの昇格](../core/promoting-properties.md)
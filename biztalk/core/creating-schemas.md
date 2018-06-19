---
title: スキーマの作成 |Microsoft ドキュメント
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
ms.openlocfilehash: ac019276923467fe2d95f5a0a0b4a7b53513e9c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238538"
---
# <a name="creating-schemas"></a>スキーマの作成
BizTalk エディターを使用して、2 つの種類のスキーマを作成することができます。 メッセージのスキーマとプロパティ スキーマです。  
  
> [!NOTE]
>  メッセージ スキーマにはいくつかの種類 (XML メッセージ スキーマ、フラット ファイル メッセージ スキーマ、およびエンベロープ スキーマ) があります。  
  
 メッセージ スキーマでは、構造を定義して、取引先やアプリケーションとの送信および受信を行うメッセージの内容を制限します。 メッセージ スキーマは、最も一般的な種類の Microsoft による使用するスキーマ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ビジネス ドキュメントと、それを格納するために使用するエンベロープの両方の XML メッセージ スキーマを作成し、フラット ファイル メッセージ スキーマ、ヘッダー、ボディ、およびトレーラーのスキーマを含むフラット ファイル拡張子 BizTalk エディターを使用して作成できます。  
  
 プロパティ スキーマは、特殊なスキーマです。 プロパティ スキーマは、インスタンス メッセージからメッセージ コンテキストに昇格されるフィールドおよびレコードのデータに使用する検証テンプレートを提供します。 プロパティ スキーマは、実行時に昇格される厳密に型指定された正式なデータを提供するために使用します。  
  
 プロパティの昇格の重要な情報をプルするための集中管理メカニズムを提供、定義したからインスタンス メッセージより簡単にアクセスできるようにする BizTalk Server コンポーネントを内でメッセージの処理を BizTalk を通過するときサーバー。 昇格させたプロパティの一般的な使用方法は、メッセージ インスタンスとサブスクリプションを照合することです。これにより、メッセージを正しくルーティングできます。  
  
 このセクションでは、BizTalk Server のさまざまなスキーマを作成する方法について説明し、複数の種類のスキーマの関連項目を示します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [プロジェクト内のスキーマを管理します。](../core/managing-schemas-within-projects.md)  
  
-   [スキーマ内のノードを管理します。](../core/managing-the-nodes-within-a-schema.md)  
  
-   [プロパティの昇格](../core/promoting-properties.md)
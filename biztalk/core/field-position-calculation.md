---
title: 位置の計算フィールド |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7e315f09-f2c9-49cc-8d2f-0f4f2d48fd45
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 55c58f532ea64300518667d677d2248f5c1c2b6b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246074"
---
# <a name="field-position-calculation"></a>フィールド位置の計算

## <a name="overview"></a>概要
使用すると、**位置指定値**と**位置指定オフセット**のプロパティ、**フィールド要素**と**フィールド属性**内のノード、フラット ファイル メッセージの位置指定レコードのレイアウトを定義するスキーマ、**開始位置**と**長さ**の列、**フラット ファイル** タブBizTalk エディターを表示する計算の開始位置と長さ、それぞれの関連するフィールドとレコード。  
  
> [!NOTE]
>  **フラット ファイル**フラット ファイル拡張機能を使用して、構成した場合、BizTalk エディターで XSD ビューの代替タブ付きビューとして タブが表示されます、**スキーマ エディター拡張機能**プロパティ、の**スキーマ**ノード。 このプロパティの詳細について[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
  
 一般に、特定のフィールドの開始位置*N*前のフィールドの開始位置と前のフィールドとフィールドの指定した (位置指定) オフセットの長さは、 *N*.  
  
 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のすべてのフィールド位置の計算は、自動的にまとめて行われるので、コマンドを実行する必要はありません (以前のバージョンの BizTalk Server では、コマンドを実行していました)。  
  
## <a name="see-also"></a>参照  
-  [位置指定レコードに関する注意点](../core/positional-record-considerations.md)   
-  **位置指定値 (フラット ファイル スキーマのノード プロパティ)** と**位置指定オフセット (フラット ファイル スキーマのノード プロパティ)**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
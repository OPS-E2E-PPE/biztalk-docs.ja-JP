---
title: フィールド位置の計算 |Microsoft Docs
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
ms.openlocfilehash: 8fb167c0bf704aee869e81798116377608fde0c2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983027"
---
# <a name="field-position-calculation"></a>フィールド位置の計算

## <a name="overview"></a>概要
使用すると、**位置指定値**と**位置指定オフセット**のプロパティ、**フィールド要素**と**フィールド属性**内のノード、フラット ファイル メッセージの位置指定レコードのレイアウトを定義するスキーマ、**開始位置**と**長さ**の列、**フラット ファイル**タブBizTalk エディターを表示する、計算の開始位置と長さ、それぞれの関連するフィールドとレコード。  

> [!NOTE]
>  **フラット ファイル** タブは、フラット ファイル拡張機能を使用して構成した場合と BizTalk エディターで XSD ビューの代替タブ付きビューとして表示、**スキーマ エディター拡張機能**プロパティ、の**スキーマ**ノード。 このプロパティについて詳しく[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。

 一般に、特定のフィールドの開始位置*N*は、前のフィールドの開始位置と、前のフィールドとフィールドに指定した (位置指定) オフセットの長さ*N*.  

 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のすべてのフィールド位置の計算は、自動的にまとめて行われるので、コマンドを実行する必要はありません (以前のバージョンの BizTalk Server では、コマンドを実行していました)。  

## <a name="see-also"></a>参照  
- [位置指定レコードに関する注意](../core/positional-record-considerations.md)   
- **位置指定値 (フラット ファイル スキーマのノード プロパティ)** と**位置指定オフセット (フラット ファイル スキーマのノード プロパティ)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]

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
ms.openlocfilehash: 160e28e23de6c792e3669831e84e582dd07c7318
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345591"
---
# <a name="field-position-calculation"></a>フィールド位置の計算

## <a name="overview"></a>概要
使用すると、**位置指定値**と**位置指定オフセット**のプロパティ、**フィールド要素**と**フィールド属性**内のノード、フラット ファイル メッセージの位置指定レコードのレイアウトを定義するスキーマ、**開始位置**と**長さ**の列、**フラット ファイル**タブBizTalk エディターを表示する、計算の開始位置と長さ、それぞれの関連するフィールドとレコード。  

> [!NOTE]
>  **フラット ファイル** タブは、フラット ファイル拡張機能を使用して構成した場合と BizTalk エディターで XSD ビューの代替タブ付きビューとして表示、**スキーマ エディター拡張機能**プロパティ、の**スキーマ**ノード。 このプロパティについて詳しく[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。

 一般に、特定のフィールドの開始位置*N*は、前のフィールドの開始位置と、前のフィールドとフィールドに指定した (位置指定) オフセットの長さ*N*.  

 Microsoft のすべてのフィールド位置の計算[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は (BizTalk Server の以前のバージョンで必要となった) コマンドを実行することがなく、-その場で、実行、自動的にします。  

## <a name="see-also"></a>参照  
- [位置指定レコードに関する注意](../core/positional-record-considerations.md)   
- **位置指定値 (フラット ファイル スキーマのノード プロパティ)** と**位置指定オフセット (フラット ファイル スキーマのノード プロパティ)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]

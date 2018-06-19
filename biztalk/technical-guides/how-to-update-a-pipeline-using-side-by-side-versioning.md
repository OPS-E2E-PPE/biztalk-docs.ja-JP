---
title: サイド バイ サイドのバージョン管理を使用してパイプラインを更新する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd884a76-71dd-4c90-b4ba-f1cd7f48eb04
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a5b977d8f0d1964df33c2b2f549bd420d0d3179
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008379"
---
# <a name="how-to-update-a-pipeline-using-side-by-side-versioning"></a>サイド バイ サイドのバージョン管理を使用してパイプラインを更新する方法
サイド バイ サイドのバージョン管理によって追加された新しいパイプラインを使用する簡単な方法は、送信ポートで、新しく展開されたパイプライン バージョンを選択または受信場所です。 これにより、古いパイプライン新しいと置き換わります。 ただし、本当のサイド バイ サイドの機能を旧バージョンとの互換性のため必要がある場合する必要がありますの新しい送信ポートを作成および受信場所と指定された新しいパイプライン バージョンにバインドします。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。  
  
### <a name="to-add-a-new-version-of-a-pipeline-component"></a>パイプライン コンポーネントの新しいバージョンを追加するには  
  
1.  Visual Studio で、パイプライン コンポーネントの新しいバージョンを作成し、そのアセンブリに署名します。  
  
2.  パイプライン コンポーネントを追加、**パイプライン コンポーネント**フォルダー (\<*インストール フォルダー*\>\Pipeline Components)。  
  
3.  パイプライン コンポーネントをパイプラインに追加します。  
  
4.  パイプラインを構築またはソリューションを展開した後からパイプライン コンポーネントを削除、**パイプライン コンポーネント**フォルダーです。  
  
5.  パイプライン コンポーネントをグローバル アセンブリ キャッシュ (GAC) に追加します。  
  
 これらの手順を完了した、パイプラインのコンパイルされたアセンブリでは、パイプライン コンポーネントの正しいバージョンを参照し、BizTalk Server で使用される AppDomain は前を検索するのではなく、GAC、パイプライン コンポーネントの新しいバージョンを見つけパイプライン コンポーネント フォルダーでのパイプライン コンポーネントのバージョンです。  
  
## <a name="see-also"></a>参照  
 [サイドバイサイドのバージョン管理を使用した更新](../technical-guides/updating-using-side-by-side-versioning.md)
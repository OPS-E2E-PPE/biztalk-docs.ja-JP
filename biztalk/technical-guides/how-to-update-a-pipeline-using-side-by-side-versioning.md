---
title: サイド バイ サイド バージョン管理を使用してパイプラインを更新する方法 |Microsoft Docs
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
ms.openlocfilehash: 85aa5f7d134e14d16fbb4fb88fcff29cf6ce672f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400271"
---
# <a name="how-to-update-a-pipeline-using-side-by-side-versioning"></a>サイド バイ サイド バージョン管理を使用してパイプラインを更新する方法
サイド バイ サイド バージョン管理によって追加された新しいパイプラインを使用する簡単な方法は、送信ポートで、新しく展開されたパイプライン バージョンを選択するか、受信場所にです。 古いパイプラインは、新しいこの置き換えられます。 ただし、後方互換性のための本当のサイド バイ サイドでの機能を必要がある場合する必要がありますの新しい送信ポートを作成および受信場所し指定されたパイプラインの新しいバージョンにバインドします。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。  
  
### <a name="to-add-a-new-version-of-a-pipeline-component"></a>パイプライン コンポーネントの新しいバージョンを追加するには  
  
1. Visual Studio で、パイプライン コンポーネントの新しいバージョンを作成し、アセンブリに署名します。  
  
2. パイプライン コンポーネントを追加、**パイプライン コンポーネント**フォルダー (\<*インストール フォルダー*\>\Pipeline Components)。  
  
3. パイプライン コンポーネントをパイプラインに追加します。  
  
4. パイプラインを構築しても、ソリューションの配置後からパイプライン コンポーネントの削除、**パイプライン コンポーネント**フォルダー。  
  
5. パイプライン コンポーネントをグローバル アセンブリ キャッシュ (GAC) に追加します。  
  
   次の手順を完了すると、コンパイル済みのパイプライン アセンブリは、パイプライン コンポーネントの正しいバージョンを参照してくださいし、BizTalk Server で使用される AppDomain は、前の検索ではなく、GAC でパイプライン コンポーネントの新しいバージョンを検索パイプライン コンポーネント フォルダーでのパイプライン コンポーネントのバージョンです。  
  
## <a name="see-also"></a>参照  
 [サイドバイサイドのバージョン管理を使用した更新](../technical-guides/updating-using-side-by-side-versioning.md)
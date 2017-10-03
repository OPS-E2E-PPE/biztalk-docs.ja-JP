---
title: "サイド バイ サイドのバージョン管理を使用してパイプラインを更新する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fd884a76-71dd-4c90-b4ba-f1cd7f48eb04
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c4e8803128f2232905229de3b5de49994e039ff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-update-a-pipeline-using-side-by-side-versioning"></a>サイド バイ サイドのバージョン管理を使用してパイプラインを更新する方法
サイド バイ サイドのバージョン管理によって追加された新しいパイプラインを使用する簡単な方法は、送信ポートで、新しく展開されたパイプライン バージョンを選択または受信場所です。 これにより、古いパイプライン新しいと置き換わります。 ただし、本当のサイド バイ サイドの機能を旧バージョンとの互換性のため必要がある場合する必要がありますの新しい送信ポートを作成および受信場所と指定された新しいパイプライン バージョンにバインドします。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。  
  
### <a name="to-add-a-new-version-of-a-pipeline-component"></a>パイプライン コンポーネントの新しいバージョンを追加するには  
  
1.  Visual Studio で、パイプライン コンポーネントの新しいバージョンを作成し、そのアセンブリに署名します。  
  
2.  パイプライン コンポーネントを追加、**パイプライン コンポーネント**フォルダー (\<*インストール フォルダー*> \Pipeline Components)。  
  
3.  パイプライン コンポーネントをパイプラインに追加します。  
  
4.  パイプラインを構築またはソリューションを展開した後からパイプライン コンポーネントを削除、**パイプライン コンポーネント**フォルダーです。  
  
5.  パイプライン コンポーネントをグローバル アセンブリ キャッシュ (GAC) に追加します。  
  
 これらの手順を完了したら、パイプラインのコンパイルされたアセンブリでは、パイプライン コンポーネントの正しいバージョンを参照およびによって使用される、AppDomain 後[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]前を検索するのではなく、gac、パイプライン コンポーネントの新しいバージョンを検索パイプライン コンポーネント フォルダーでのパイプライン コンポーネントのバージョンです。  
  
## <a name="see-also"></a>参照  
 [サイド バイ サイドのバージョン管理を使用して更新](../technical-guides/updating-using-side-by-side-versioning.md)
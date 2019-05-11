---
title: JMS MQRFH2 サンプルの依存関係と強力なキー名の定義 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a3a5cdce-dcdf-48df-91a5-8cf2afce9255
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7079bc7475fa8310d64ff6925dd89e348afc195
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65261532"
---
# <a name="jms-mqrfh2-sample-dependencies-and-strong-key-name-definition"></a>JMS MQRFH2 サンプルの依存関係と強力なキー名の定義
Visual Studio のプロジェクトの ESB です。JMS します。PipelineComponents は、次のフォルダーに依存します。  
  
-   \<BizTalk Server のインストール ディレクトリ\>します。 このフォルダーは、次の名前空間へのアクセスを提供します。  
  
    -   **Microsoft::BizTalk::Message::Interop**  
  
    -   **Microsoft::BizTalk::Component::Interop**  
  
## <a name="the-strong-name-key-definition"></a>厳密な名前キーの定義  
 通常、厳密な名前キーの定義は、AssemblyInfo.cpp ファイルに存在します。 ただし、これと競合する、 C++ AssemblyInfo.cpp ファイルの読み取り後に、コンパイラがアセンブリに追加するマニフェスト ファイル。 この競合は、グローバル アセンブリ キャッシュにファイルを配置するあらゆる試みをできなくなります。 代わりに、リンカーにあるキー ファイルを指定することで、厳密な名前キー ファイルを制御./../../../../../Keys/Microsoft.Practices.ESB.snk します。 この値を編集するには、次のオプションの設定に移動します。  
  
 ESB します。JMS します。スキーマ  
  
 \- プロジェクト  
  
 \- -プロパティ  
  
 \- -構成プロパティ  
  
 \- ---リンカー  
  
 \- ----詳細  
  
 \- ----キー ファイル  
  
> [!NOTE]
>  JMS のパイプライン コンポーネントを構築する場合は、前述のように、厳密な名前キー ファイルへの参照を削除する AssemblyInfo.cpp ファイルを編集する必要があります。 その後の編集、**キー ファイル**厳密な名前キー ファイルの名前とパスを指定する高度なプロパティ、リンカーのオプション。
---
title: "JMS MQRFH2 サンプルの依存関係と強力なキー名の定義 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a3a5cdce-dcdf-48df-91a5-8cf2afce9255
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f71915866e807bea8cbd9fdcbf0b1b7ac38a505
ms.sourcegitcommit: 6b6d905bbef7796c850178e99ac293578bb58317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2017
---
# <a name="jms-mqrfh2-sample-dependencies-and-strong-key-name-definition"></a>JMS MQRFH2 サンプルの依存関係と強力なキー名の定義
Visual Studio プロジェクト ESB です。JMS です。PipelineComponents は、次のフォルダーに依存します。  
  
-   \<BizTalk Server のインストール ディレクトリ >。 このフォルダーは、次の名前空間へのアクセスを提供します。  
  
    -   **Microsoft::BizTalk::Message::Interop**  
  
    -   **Microsoft::BizTalk::Component::Interop**  
  
## <a name="the-strong-name-key-definition"></a>厳密な名前キーの定義  
 通常、厳密な名前キーの定義は、AssemblyInfo.cpp ファイルに存在します。 ただし、AssemblyInfo.cpp ファイルの読み取り後に、コンパイラがアセンブリに追加された C++ マニフェスト ファイルと競合します。 この競合は、グローバル アセンブリ キャッシュにファイルを配置するあらゆる試みをできなくなります。 代わりに、リンカーにある、キー ファイルを指定することによって、厳密な名前キー ファイルを制御./../../../../../Keys/Microsoft.Practices.ESB.snk です。 この値を編集するには、次のオプションの設定に移動します。  
  
 ESB です。JMS です。スキーマ  
  
 \- プロジェクト  
  
 \--プロパティ  
  
 \--構成プロパティ  
  
 \----リンカー  
  
 \-----詳細  
  
 \-含みますキー ファイル  
  
> [!NOTE]
>  JMS パイプライン コンポーネントを作成している場合は、前述のように、厳密な名前キー ファイルへの参照を削除する AssemblyInfo.cpp ファイルを編集する必要があります。 コピー後、編集、**キー ファイル**リンカーの詳細プロパティのパスと厳密な名前キー ファイルの名前を指定するオプションです。
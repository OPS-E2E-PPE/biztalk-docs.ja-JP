---
title: "パイプライン コンポーネントの展開 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, pipeline components [custom]
- pipeline components [custom], deploying
ms.assetid: 98b47fbf-62c0-4012-a406-58c4d56b305a
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 041bd8c6e6fa9c3969be18f0804460c00de5f11a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="deploying-pipeline-components"></a>パイプライン コンポーネントの展開
すべての .NET パイプライン コンポーネント アセンブリ (ネイティブおよびカスタム) がである必要があります、 \<*インストール ディレクトリ*\>サーバーによって実行される \Pipeline Components フォルダーです。 カスタム コンポーネントを持つパイプラインを複数のサーバーに展開するには、各サーバー上の指定のフォルダーに、コンポーネントのバイナリが存在する必要があります。  
  
 BizTalk ランタイムで使用するカスタム パイプライン コンポーネントを、グローバル アセンブリ キャッシュ (GAC) に追加する必要はありません。  
  
 パイプラインのカスタム COM コンポーネントも、そのコンピューターに COM コンポーネントとして登録されている限り、ツールボックスに表示されます。 カスタム .NET パイプライン コンポーネントを配置する必要があります、 \<*インストール ディレクトリ*\>\Pipeline Components フォルダーです。  
  
 バイナリ ファイルを正しい場所に配置した後、コンポーネントをツールボックスに追加する必要があります。 パイプライン コンポーネントをツールボックスに追加する方法の詳細については、次を参照してください。[ツールボックスの使用方法](../core/how-to-use-the-toolbox.md)です。  
  
## <a name="see-also"></a>参照  
 [カスタム パイプライン コンポーネントの開発](../core/developing-custom-pipeline-components.md)
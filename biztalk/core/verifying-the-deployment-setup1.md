---
title: "展開 Setup1 の検証 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- CLASSPATH, verifying
- deployment, verifying setup
ms.assetid: 6c719e4c-9a61-480f-a4e4-0a1c518d1364
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5799d164dc2470236c3ab0286e38d19986a4d5a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="verifying-the-deployment-setup"></a>展開セットアップの確認
BizTalk Server を使用してバインド ファイルをインポートする前に、以下の項目について確認する必要があります。  
  
-   CLASSPATH が JD Edwards EnterpriseOne 固有のファイルの特定の場所を指している。 新しいコンピューターで、これらのファイルの場所が同じであることを確認します。同じでない場合は、バインド ファイルを編集します。  
  
-   新しいコンピューターに、応答用の同じフォルダーが存在する。同じでない場合は、バインド ファイルを編集します。  
  
-   JD Edwards EnterpriseOne システム パスワードが構成に存在する場合、パスワードが ***** としてバインド ファイルに保存されている。 詳細については、次を参照してください。[展開の制限事項](../core/deployment-limitations4.md)です。  
  
## <a name="see-also"></a>参照  
 [ポートとアセンブリの展開](../core/deploying-ports-and-assemblies3.md)
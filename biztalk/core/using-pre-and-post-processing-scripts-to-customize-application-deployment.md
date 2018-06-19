---
title: 前処理および後処理のスクリプト アプリケーション展開のカスタマイズを使用した |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- customizing, applications
- applications, customizing
- scripts, applications
- scripts, customizing
ms.assetid: 47627394-d594-491b-9098-38c5d028a378
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7dc0afd7ed042f475a9a008125c968f401e6df92
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287170"
---
# <a name="using-pre--and-post-processing-scripts-to-customize-application-deployment"></a>処理前および処理後のスクリプトを使用したアプリケーション展開のカスタマイズ
このセクションの各トピックでは、アプリケーションのインポート、インストール、またはアンインストール時にアクションを実行する処理前または処理後のスクリプトを作成する方法について説明します。 処理前のスクリプトは、アプリケーションのインポートまたはインストールの開始前、およびアンインストールの完了後に 1 つのアクションまたはアクションのセットを実行します。 処理後のスクリプトは、アプリケーションのインポートまたはインストールの完了後、あるいはアンインストールの開始前に 1 つのアクションまたはアクションのセットを実行します。  
  
 たとえば、リソース ファイルをインストール中に上書きされる前にバックアップするには、インストールの前に実行する処理前のスクリプトを追加する必要があります。 また、アプリケーションのインストール後に証明書ストアに証明書を追加するには、処理後のスクリプトを実行する必要があります。  
  
> [!NOTE]
>  BizTalk Server には、処理前のスクリプトと処理後のスクリプトのサンプルが用意されています。 サンプル スクリプトの使用方法の詳細については、次を参照してください。[テンプレート (アプリケーションの展開サンプル)](../core/template-application-deployment-sample.md)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [処理前または処理後のスクリプトを作成します。](../core/creating-a-pre-or-post-processing-script.md)  
  
-   [環境変数が展開の状態を指定する方法](../core/how-environment-variables-indicate-deployment-state.md)  
  
-   [配置時にファイルのアイテムの状態](../core/status-of-file-artifacts-during-deployment.md)  
  
-   [前処理および後処理のスクリプト環境変数](../core/pre-and-post-processing-script-environment-variables.md)
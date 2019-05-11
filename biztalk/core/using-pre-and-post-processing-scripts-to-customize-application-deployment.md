---
title: 前処理および後処理のスクリプトを使用したアプリケーション展開のカスタマイズ |Microsoft Docs
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
ms.openlocfilehash: 23734f43a479e4e526535b61f0e9b957752e03d3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396584"
---
# <a name="using-pre--and-post-processing-scripts-to-customize-application-deployment"></a>前処理および後処理のスクリプトを使用したアプリケーション展開のカスタマイズ
このセクションのトピックでは、事前作成する方法を記述またはアプリケーションがインポートされるときにアクションを実行する処理後のスクリプトは、インストール、またはアンインストールします。 処理前のスクリプトでは、アプリケーションのインポートまたはインストールの開始前に、およびアンインストールの完了後にアクションまたは一連のアクションを実行します。 処理後のスクリプトでは、アプリケーションのインポートまたはインストールの完了後、またはアンインストールの開始前に、アクションまたはアクションのセットを実行します。  
  
 たとえば、インストール中に上書きされる前に、リソース ファイルをバックアップしてインストールする前に実行される処理前のスクリプトを追加する場合があります。 または、アプリケーションをインストールした後、証明書ストアに証明書の追加の処理後のスクリプトを実行したい場合があります。  
  
> [!NOTE]
>  BizTalk Server には、サンプルの前処理および後処理のスクリプトが含まれています。 サンプル スクリプトの使用方法の詳細については、次を参照してください。 [Template (アプリケーションの展開サンプル)](../core/template-application-deployment-sample.md)します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [処理前または処理後のスクリプトの作成](../core/creating-a-pre-or-post-processing-script.md)  
  
-   [環境変数と展開状態の対応関係](../core/how-environment-variables-indicate-deployment-state.md)  
  
-   [展開中のファイル アイテムの状態](../core/status-of-file-artifacts-during-deployment.md)  
  
-   [処理前および処理後のスクリプト環境変数](../core/pre-and-post-processing-script-environment-variables.md)
---
title: 例外処理サービス サンプルを実行している |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d69e720c-89e4-42c2-b4d0-31f0b865ab7f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17a1460b1248aa64ba043e8e6c01a66dc6215490
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242849"
---
# <a name="running-the-exception-handling-service-sample"></a>例外処理サービス サンプルを実行しています。
例外処理サービス サンプルでは、外部アプリケーションから、例外処理の ESB フレームワークにエラーを送信するには、例外処理の Web サービスを使用する方法を示します。 このサンプルを実行するには、次の手順が必要です[例外管理サンプルをインストールする](../esb-toolkit/installing-the-exception-management-samples.md)します。  
  
 **例外処理サービス サンプルを実行するには**  
  
1. Windows エクスプ ローラーで開くフォルダーの \Source\Samples\ExceptionHandlingService、インストールされている、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]サンプルの場合と、ExceptionHandlingService.sln という名前の Visual Studio ソリューション ファイルを開きます。  
  
2. Visual Studio で、次のようにクリックします。**デバッグの開始**ツールバー。  
  
3. フォームを読み込みますが、をクリックして、**生成例外**ボタンをクリックします。  
  
4. Windows エクスプ ローラーでフォルダー \Samples\Exception Handling\Test\Filedrop\All_Exceptions を開き、最新の Exceptions_ {GUID} .xml ファイルを開きます。  
  
5. 生成された例外の内容を確認します。  
  
   例外処理サービス サンプルが、例外管理サービスを使用する方法についての詳細については、次を参照してください。 [、例外処理サービス サンプルのしくみ](../esb-toolkit/how-the-exception-handling-service-sample-works.md)します。
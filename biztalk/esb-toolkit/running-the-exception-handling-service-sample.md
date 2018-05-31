---
title: 例外処理サービスのサンプルを実行している |Microsoft ドキュメント
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
ms.openlocfilehash: 8dd7c87e84cf7e6e107fc110c611369d0407e003
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007787"
---
# <a name="running-the-exception-handling-service-sample"></a>例外処理サービスのサンプルを実行しています。
例外処理サービスのサンプルでは、外部アプリケーションから、例外処理の ESB フレームワークにはエラーを送信するために、例外処理の Web サービスを使用する方法を示します。 このサンプルを実行するため、次の手順が必要です[例外管理のサンプルをインストールする](../esb-toolkit/installing-the-exception-management-samples.md)です。  
  
 **例外処理サービス サンプルを実行するには**  
  
1.  Windows エクスプ ローラーで、インストールされている、フォルダー \Source\Samples\ExceptionHandlingService を開き、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]サンプルを開き、ExceptionHandlingService.sln をという名前の Visual Studio ソリューション ファイルです。  
  
2.  Visual Studio で、[**デバッグの開始]** ツールバー。  
  
3.  フォームを読み込みますが、をクリックして、**生成例外**ボタンをクリックします。  
  
4.  Windows エクスプ ローラーで、フォルダー \Samples\Exception Handling\Test\Filedrop\All_Exceptions を開き、最新の Exceptions_ {GUID} .xml ファイルを開きます。  
  
5.  生成された例外の内容を確認します。  
  
 例外処理サービスのサンプルが、例外管理サービスを使用する方法に関する詳細については、次を参照してください。 [「例外の処理サービス サンプルの動作](../esb-toolkit/how-the-exception-handling-service-sample-works.md)です。
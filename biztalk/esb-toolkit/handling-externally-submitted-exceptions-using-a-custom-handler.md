---
title: "カスタム ハンドラーを使用して例外を送信する外部の処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 53fa661e-d391-47c0-92d5-1d0c45b5963d
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ba3fc49756619f77188f0a311ff46eb18e7f0b1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="handling-externally-submitted-exceptions-using-a-custom-handler"></a>カスタム ハンドラーを使用して例外を送信する外部の処理
このユース ケースでは、外部のクライアントは、Web サービスを通じた例外メッセージを送信します。 ESB 例外エンコーダ パイプライン コンポーネントでは、事前に構成されて、送信ポート、フォールト メッセージをサブスクライブします。処理し、表示できる Microsoft InfoPath を使用して図 1 に示すようにディスク ファイルとしてが引き続き発生します。  
  
 ![外部例外の処理](../esb-toolkit/media/ch3-handlingexternalexceptions.gif "Ch3 HandlingExternalExceptions")  
  
 **図 1**  
  
 **着信の例外またはエラー メッセージを処理し、ディスク ファイルに保存します。**  
  
 例外処理サービス サンプルに含まれている、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このユース ケースを示しています。 格納される外部のアプリケーションからのエラー メッセージを送信する汎用メカニズムとして、ESB 例外サービスを使用する方法を示しています、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]例外管理データベース。 詳細については、次を参照してください。[例外処理サービス サンプルを実行している](../esb-toolkit/running-the-exception-handling-service-sample.md)です。
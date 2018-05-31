---
title: SQL アダプタのサンプルを実行している |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 13566d08-7a59-4065-b0d7-19ae2765555e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf04c06a1ef96974912ce3affe278d5a98936325
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294794"
---
# <a name="running-the-sql-adapter-sample"></a>SQL アダプタのサンプルを実行しています。
SQL アダプタ サンプルでは、行程入り口サンプルに用意されている、テスト クライアントの Windows フォーム アプリケーションを使用します。  
  
 **SQL アダプタ サンプルを実行するには**  
  
1.  GlobalBank.ESB アプリケーションが既に実行されていない場合は、Microsoft BizTalk 管理コンソールを使用して、開始します。  
  
2.  Windows エクスプ ローラーでフォルダー \Source\Samples\Itinerary\Source\ESB を開きます。インストールした Itinerary.Test、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]サンプル、および Esb.Itinerary.Test.exe をという名前のアプリケーションを開始します。  
  
3.  クリア、**を使用して WCF サービス**クライアント側の日程を使用できるようにするチェック ボックスをオンします。  
  
4.  選択、 **2 つの方法サービス**オプション  
  
5.  クリックして、**ロード行程**ボタンをクリックし、フォルダー \Source\Samples\SqlAdapter \Itineraries にあるサンプルの日程のいずれかを選択します。  
  
6.  クリックして、 **LoadMessage**ボタンをクリックし、フォルダー \Source\Samples\SqlAdapter \Test で OrderDoc.xml サンプル メッセージを選択します。  
  
7.  クリックして、 **SubmitRequest**行程入り口サービスに要求を送信するボタンをクリックします。  
  
8.  1 つの行は GlobalBankESB データベースの Product テーブルに挿入することを確認します。  
  
 SQL Adapter サンプルのしくみについては、次を参照してください。 [「SQL アダプタ サンプルの動作](../esb-toolkit/how-the-sql-adapter-sample-works.md)です。
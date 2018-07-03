---
title: SQL アダプター サンプルを実行する |Microsoft Docs
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
ms.openlocfilehash: 505f60d287b82b5650855870329e9a18496d63f1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979075"
---
# <a name="running-the-sql-adapter-sample"></a>SQL アダプター サンプルを実行します。
SQL Adapter サンプルは、行程導入サンプルで提供される Windows フォームのテスト クライアント アプリケーションを使用します。  
  
 **SQL アダプター サンプルを実行するには**  
  
1. GlobalBank.ESB アプリケーションが実行されていない場合は、Microsoft の BizTalk 管理コンソールを使用して、開始します。  
  
2. Windows エクスプ ローラーでフォルダー \Source\Samples\Itinerary\Source\ESB を開きます。インストールした Itinerary.Test、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]サンプルをし、Esb.Itinerary.Test.exe という名前のアプリケーションを起動します。  
  
3. クリア、 **WCF サービスを使用して**クライアント側の旅行プランを使用できるようにチェック ボックスをオンします。  
  
4. 選択、**方法の 2 つのサービス**オプション  
  
5. をクリックして、**ロード行程**ボタンをクリックし、フォルダー \Source\Samples\SqlAdapter \Itineraries 内にあるサンプルのスケジュールのいずれかを選択します。  
  
6. をクリックして、 **LoadMessage**ボタンをクリックし、フォルダー \Source\Samples\SqlAdapter \Test で OrderDoc.xml サンプル メッセージを選択します。  
  
7. をクリックして、 **SubmitRequest**行程入口サービスに要求を送信するボタンをクリックします。  
  
8. GlobalBankESB データベースの Product テーブル内 1 つの行が挿入されることを確認します。  
  
   SQL アダプター サンプルのしくみについては、次を参照してください。 [、SQL アダプター サンプルのしくみ](../esb-toolkit/how-the-sql-adapter-sample-works.md)します。
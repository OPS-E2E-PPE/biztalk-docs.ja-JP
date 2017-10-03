---
title: "カスタムの Itinerary シナリオを実行 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6fd69e29-e853-4b16-9966-29ab98dd5bea
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8659c5b37cba0520fb4a4c0f4c63c8d6ecff37be
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="execute-a-custom-itinerary-scenario"></a>カスタムの Itinerary シナリオを実行します。
行程テスト クライアントを使用するアプリケーションでカスタムの itinerary シナリオを実行します。  
  
### <a name="to-execute-a-custom-itinerary-scenario-using-the-itinerary-test-client-application"></a>行程テスト用クライアント アプリケーションを使用してカスタム itinerary シナリオを実行するには  
  
1.  Windows エクスプ ローラーでフォルダー \Source\Samples\Itinerary\Source\ESB を開きます。インストールした Itinerary.Test\bin\Debug、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]サンプリングし、Esb.Itinerary.Test.exe をという名前のアプリケーションを開始します。  
  
2.  サービスの種類を選択、 **ServiceType**ドロップダウン リストが、要求の名前を指定し、、 **IsRequestResponse**これは、要求/応答操作の場合はチェック ボックスです。 双方向の操作を指定し、WCF サービスのバージョンは、行程 Web; を使用します。これを行うには、チェック ボックスをオンに、 **Web サービス オプション**アプリケーション ウィンドウの上部にあるセクションです。  
  
3.  選択したサービスで使用する競合回避モジュールを指定する、 **AddResolversfortheService**ウィンドウの、競合回避モジュールは、ドロップダウン リストから、入力し、をクリックして**AddResolver**です。 必要な場合は、複数の競合回避モジュールを追加できます。 必要なすべての競合回避モジュールを追加した後にをクリックして、 **AddService**旅行計画にこのサービスの呼び出しを追加するボタンをクリックします。  
  
4.  旅行計画に複数のサービスの呼び出しを追加する場合は、手順 2. および 3. を繰り返します。 使用することも、 **RemoveService**と**ClearServices**旅行計画内のサービスのリストを変更するボタンです。  
  
5.  別の時に現在の旅程を繰り返す場合は、現在の完全な旅程をディスクに保存 をクリックして、 **SaveItinerary**ボタンをクリックします。 クリックして再度読み込むことができます、 **LoadItinerary**ボタンをクリックします。 これは、別のメッセージや行程 Web サービスの設定では、このシナリオを実行するたびに、旅行計画で、サービスとの競合回避モジュールを指定する必要はないことを意味します。  
  
6.  適切なメッセージを読み込みます。 内のメッセージの名前とパスを入力するかそのためには、 **LoadMessage**テキスト ボックスまたは省略記号ボタン (...) をクリックし、必須のメッセージ ファイルを選択します。  
  
7.  クリックして、 **SubmitRequest** itinerary に指定した設定で処理するため、メッセージを送信するボタンをクリックします。 処理には、結果が返された場合に表示されます、**結果**テキスト ボックス。
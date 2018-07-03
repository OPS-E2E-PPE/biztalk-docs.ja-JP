---
title: カスタム スケジュール シナリオの実行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6fd69e29-e853-4b16-9966-29ab98dd5bea
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9dc7b746f636b6f90462d296f12827fb0492dd23
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009555"
---
# <a name="execute-a-custom-itinerary-scenario"></a>カスタム スケジュール シナリオを実行します。
旅行プランのテスト クライアントを使用するアプリケーションでカスタム スケジュール シナリオを実行します。  

### <a name="to-execute-a-custom-itinerary-scenario-using-the-itinerary-test-client-application"></a>旅行プランのテスト用クライアント アプリケーションを使用して、カスタム スケジュール シナリオを実行するには  

1. Windows エクスプ ローラーでフォルダー \Source\Samples\Itinerary\Source\ESB を開きます。インストールした Itinerary.Test\bin\Debug、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]をサンプリングし、Esb.Itinerary.Test.exe という名前のアプリケーションを開始します。  

2. サービスの種類を選択、 **ServiceType**ボックスの一覧は、要求の名前を指定し、、 **IsRequestResponse**場合、これは、要求/応答操作のチェック ボックス。 双方向の操作を指定し、旅行プランの Web サービスの WCF のバージョンを使用します。これを行うには、チェック ボックスを選択、 **Web サービス オプション**アプリケーション ウィンドウの上部にあるセクション。  

3. 選択したサービスを使用する競合回避モジュールを指定する、 **AddResolversfortheService** 、ウィンドウで、競合回避モジュールがドロップダウン リストから入力し、クリックしての**AddResolver**します。 必要な場合は、1 つ以上の競合回避モジュールを追加できます。 必要なすべての競合回避モジュールを追加する をクリックして、 **AddService**旅行計画にこのサービスの呼び出しを追加するボタンをクリックします。  

4. 旅行計画に複数のサービス呼び出しを追加する場合は、手順 2. および 3. を繰り返します。 使用することも、 **RemoveService**と**ClearServices**旅行プラン サービスの一覧を変更するボタン。  

5. 別の時に現在のスケジュールを繰り返す場合は、完全な現在の旅程をディスクに保存 をクリックして、 **SaveItinerary**ボタンをクリックします。 クリックして再度読み込むことができます、 **LoadItinerary**ボタンをクリックします。 これは、サービスとの競合回避モジュールは、さまざまなメッセージまたはスケジュールの Web サービスの設定では、このシナリオを実行するたびに、旅行計画で指定する必要はないことを意味します。  

6. 適切なメッセージを読み込みます。 内のメッセージの名前とパスを入力するかこれを行う、 **LoadMessage**テキスト ボックスまたは省略記号ボタン (...) をクリックし、必要なメッセージ ファイルを選択します。  

7. をクリックして、 **SubmitRequest**に指定したスケジュールの設定を使用する処理のメッセージを送信するボタンをクリックします。 処理結果を返す場合に表示されます、**結果**テキスト ボックス。

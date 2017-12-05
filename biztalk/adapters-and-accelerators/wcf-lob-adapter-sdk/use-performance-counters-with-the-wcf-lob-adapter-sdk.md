---
title: "WCF LOB Adapter SDK のパフォーマンス カウンターを使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6b928eaf-2ab6-40a6-a1dd-804d4e89541e
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6bfff208920b25ee1a22aa2c3c74feeba42f4b43
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="use-performance-counters-with-the-wcf-lob-adapter-sdk"></a>WCF LOB Adapter SDK を使用するパフォーマンス カウンター
自動的に実行しているローカルまたはリモート コンピューターからパフォーマンス データを収集するパフォーマンス ツールを使用することができます、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。 開始を定義して自動ログ生成の時間を停止、および 1 つのコンソール ウィンドウで、複数のログ セッションを管理するか、およびを送信するメッセージを有効にするコンピューターや、条件が満たされたときに開始するログに警告を設定できます。 このトピックでのパフォーマンス カウンターについて説明します、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。  
  
## <a name="performance-objects-and-counters"></a>パフォーマンス オブジェクトおよびカウンター  
 インストールするときに、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、「ServiceModel アダプター」をという名前の 1 つのパフォーマンス オブジェクトがインストールされています。 パフォーマンス オブジェクトには、多くさまざまなパフォーマンス カウンターにはが含まれています。 パフォーマンス オブジェクトは、特定のリソース、アプリケーション、またはサービスの動作状況を測定します。 パフォーマンス オブジェクトおよびカウンターのパフォーマンス データの取得、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、機能、およびサービス コンピューターで使用されます。 このパフォーマンス データは通常、データを生成するコンポーネントの名前します。 パフォーマンス カウンターは、特定の情報または特定のパフォーマンス オブジェクトのデータを収集するために使用されます。  
  
 ServiceModel のアダプターのパフォーマンス オブジェクトからカウンターを選択すると、ときにのみについて特定のアダプターのインスタンスをインスタンスのインスタンスの選択リストから選択して監視することもできます。 各アダプター インスタンスは、の形式で表示されます\<ProcessId\>@\<ConnectionString\>です。 たとえば、 115@echo:(& a) #124; &#124; ホスト &#124; temp しますか? echoprefix = 前が 115 のプロセスで実行されている echo アダプター インスタンスを示すです。  
  
 WCF でのパフォーマンス カウンターについては、次を参照してください。 [WCF パフォーマンス カウンタ](https://msdn.microsoft.com/library/ms735098.aspx)です。
  
### <a name="servicemodel-adapters-metadata-cache-performance-counters"></a>ServiceModel アダプターのメタデータ キャッシュのパフォーマンス カウンター  
 次の表に、キャッシュ パフォーマンス カウンターを監視するために使用する、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。  
  
|カウンター|Description|  
|-------------|-----------------|  
|% キャッシュ ヒットの読み取り|メタデータの割合は、アダプターのキャッシュのヒットを読み取る。|  
|メタデータの解決|アダプターによって解決されたメタデータ項目の数。|  
|キャッシュがいっぱい %|使用中のキャッシュ サイズの制限の割合です。|  
  
### <a name="servicemodel-adapters-connection-performance-counters"></a>ServiceModel アダプター接続のパフォーマンス カウンター  
 次の表に、接続のパフォーマンス カウンターを監視するために使用する、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。  
  
|カウンター|Description|  
|-------------|-----------------|  
|中止された接続|中止されたターゲット システム接続の数。|  
|使用中の接続|使用中のターゲット システム接続の数。|  
|開いている接続|現在開いている対象システム接続の数。|  
|接続の準備完了|使用可能なターゲット システム接続の数。|  
|保留中の接続要求|保留中の数は、システムの接続要求を対象します。|  
  
### <a name="servicemodel-adapters-message-exchange-performance-counters"></a>ServiceModel アダプターのメッセージ交換のパフォーマンス カウンター  
 次の表に、監視に使用できるメッセージ交換パフォーマンス カウンター、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。  
  
|カウンター|Description|  
|-------------|-----------------|  
|送信呼び出し|ターゲット システムに、アダプターからの送信呼び出しの数です。|  
|1 秒あたりの送信呼び出し|ターゲット システムに、アダプターから 1 秒あたりの送信呼び出しの数です。|  
  
## <a name="see-also"></a>参照  
 [WCF LOB Adapter SDK を使用して作成されたアダプターをトラブルシューティングします。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/troubleshoot-adapter-created-using-the-wcf-lob-adapter-sdk.md)
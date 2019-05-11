---
title: WCF LOB アダプター SDK を使用したパフォーマンス カウンターの使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6b928eaf-2ab6-40a6-a1dd-804d4e89541e
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a26ce33b8e8b191757c7f2cfc212cde4f5c24ed4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362692"
---
# <a name="use-performance-counters-with-the-wcf-lob-adapter-sdk"></a>WCF LOB アダプター SDK を使用したパフォーマンス カウンターを使用します。
自動的に実行しているローカルまたはリモート コンピューターからパフォーマンス データを収集するパフォーマンス ツールを使用することができます、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。 開始を定義して自動ログ生成の時間を停止、および 1 つのコンソール ウィンドウで、複数のログ セッションを管理するか、およびメッセージを送信できるようにするコンピューター上で、条件が満たされたときに開始するログ アラートを設定できます。 このトピックでは説明用のパフォーマンス カウンター、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。  
  
## <a name="performance-objects-and-counters"></a>パフォーマンス オブジェクトおよびカウンター  
 インストールするときに、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、「ServiceModel アダプター」という名前の 1 つのパフォーマンス オブジェクトがインストールされています。 パフォーマンス オブジェクトには、さまざまなパフォーマンス カウンターが含まれます。 パフォーマンス オブジェクトは、特定のリソース、アプリケーション、またはサービスの動作状況を測定します。 パフォーマンス オブジェクトおよびカウンターのパフォーマンス データの取得、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、機能、およびサービスのコンピューターに使用するためです。 このパフォーマンス データは通常、データを生成するコンポーネントの名前します。 パフォーマンス カウンターは、特定の情報または特定のパフォーマンス オブジェクトのデータを収集するために使用されます。  
  
 ServiceModel のアダプターのパフォーマンス オブジェクトからカウンターを選択するときにのみインスタンスの選択リストから、インスタンスを選択して情報の特定のアダプターのインスタンスを監視することもできます。 各アダプター インスタンスは、の形式で表示されます\<ProcessId\>@\<ConnectionString\>します。 たとえば、 115@echo: &#124;&#124;ホスト&#124;temp でしょうか。 echoprefix = 115 のプロセスで実行されているエコー アダプターのインスタンスが前にことを示します。  
  
 WCF でのパフォーマンス カウンターについては、次を参照してください。 [WCF パフォーマンス カウンタ](https://msdn.microsoft.com/library/ms735098.aspx)します。
  
### <a name="servicemodel-adapters-metadata-cache-performance-counters"></a>ServiceModel アダプター メタデータのキャッシュのパフォーマンス カウンター  
 次の表に、キャッシュのパフォーマンス カウンターを監視するために使用できる、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。  
  
|カウンター|説明|  
|-------------|-----------------|  
|% キャッシュ ヒット数の読み取り|メタデータの割合は、アダプター キャッシュのヒットを読み取る。|  
|メタデータの解決|アダプターによって解決されたメタデータ項目の数。|  
|キャッシュがいっぱい %|使用中のキャッシュ サイズの制限の割合。|  
  
### <a name="servicemodel-adapters-connection-performance-counters"></a>ServiceModel アダプター接続のパフォーマンス カウンター  
 次の表に、接続のパフォーマンス カウンターを監視するために使用できる、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。  
  
|カウンター|説明|  
|-------------|-----------------|  
|中止された接続|中止されたターゲット システムの接続の数。|  
|使用中の接続|現在使用中のターゲット システムの接続の数。|  
|開いている接続|現在開いている対象システムの接続の数。|  
|接続の準備完了|使用可能なターゲット システムの接続の数。|  
|保留中の接続要求|保留中の数はターゲット システムの接続要求です。|  
  
### <a name="servicemodel-adapters-message-exchange-performance-counters"></a>ServiceModel アダプターのメッセージ交換のパフォーマンス カウンター  
 次の表に、監視に使用できるメッセージ交換パフォーマンス カウンター、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。  
  
|カウンター|説明|  
|-------------|-----------------|  
|発信呼び出し|ターゲット システムにアダプターから送信呼び出しの数。|  
|1 秒あたりの送信呼び出し|ターゲット システムにアダプターから 1 秒あたりの送信呼び出しの数。|  
  
## <a name="see-also"></a>参照  
 [WCF LOB Adapter SDK を使用して作成されたアダプターをトラブルシューティングします。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/troubleshoot-adapter-created-using-the-wcf-lob-adapter-sdk.md)
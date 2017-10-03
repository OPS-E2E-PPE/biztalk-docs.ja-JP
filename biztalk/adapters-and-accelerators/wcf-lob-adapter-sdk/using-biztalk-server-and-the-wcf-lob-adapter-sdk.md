---
title: "BizTalk Server と WCF LOB Adapter SDK を使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 43ff0357-76e6-42bc-a1f7-0385d9378a5f
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41fffdf81d6e5565f9799594ddee485be485fed4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-biztalk-server-and-the-wcf-lob-adapter-sdk"></a>BizTalk Server と WCF LOB Adapter SDK を使用します。
このセクションには、リレーションシップに関する情報が含まれています。[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。 このセクションに含まれる情報が各によって提供される 2 つの異なるフレームワークの比較が含まれています、移行するためのヒント、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]カスタム アダプター。  
  
## <a name="relationship-with-the-sdk-and-biztalk-server"></a>SDK および BizTalk Server との関係
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]SDK とツールおよび操作とデータの動的なセットを含む基幹業務システム用の高度なアダプターを作成する開発者を有効にするコンポーネントのセットを提供します。 アダプターは、WCF カスタム バインドとして公開され、そのため、WCF バインディングで使用できるアプリケーションで使用できることができます。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]メッセージ フローと多様な企業のシステム間で調整できる製品は、します。間の通信[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アダプターでを外部のメッセージを取得し、処理に適した形式に変換する処理は外部システムと[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。  
  
 これら 2 つのテクノロジに共通の[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]WCF アダプター。 WCF で公開されるバインディングを使用して操作とで記述されたアダプターによって公開されているデータを使用するため、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。  
  
 次の図は、内で、BizTalk WCF アダプターと WCF LOB アダプターを使用する方法の大まかな概要を提供する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ターゲット LOB システムと通信します。  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/8dd622c6-ab5e-4cd9-aa86-5176f5c62203.gif "8dd622c6-ab5e-4cd9-aa86-5176f5c62203")  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/4f503084-da4f-41cb-92b9-eaea25d1b456.gif "4f503084-da4f-41cb-92b9-eaea25d1b456")  

## <a name="differences-between-the-sdk-and-the-biztalk-server-adapter-framework"></a>SDK と、BizTalk Server アダプター フレームワークの相違点

両方の[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]と[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アダプター フレームワークは、カスタム アダプターを作成するため、SDK を提供がありますがサポート量の重要な違い API の観点から提供されるツールおよびしても、再利用性、アダプターの 1 回では完了しました。  
  
 2 つのフレームワークの主な違いの一部は、次の表にまとめたものです。  
  
|機能|[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]|[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アダプター フレームワーク|  
|---|---|---|  
|API (API)|[!INCLUDE[dotnet45](../../includes/dotnet45-md.md)]および[!INCLUDE[dotnet451](../../includes/dotnet451-md.md)]アセンブリは、処理、接続の管理、およびメッセージングのメタデータのヘルプ クラスを提供|COM では、アダプターの操作の基本的なサポートを提供します。|  
|アダプターの公開|WCF のバインドとして公開WCF バインディングで使用できる任意のアプリケーションで使用できます。|のみ公開される[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]以外の他のアプリケーションで再利用ができません。|  
|ツール|[!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]でのメタデータ ブラウザー[!INCLUDE[btsVStudioNet](../../includes/btsvstudionet-md.md)]|n/a|  
|機能拡張|はい (として WCF チャネルの拡張機能)|不可|  
  
 BizTalk アダプター フレームワークを使用して作成されたアダプターは、BizTalk Server 内でのみから利用できます。 その一方で、アダプターに書き込まれる、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]カスタム WCF バインドとして表示されます。 ある実用上の任意の .NET サービスを利用するすべてのアプリケーションに手を拡大このアプリケーションを含む[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 内で WCF ベース アダプターが使用される[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]BizTalk WCF アダプターを使用して、ネイティブの BizTalk アダプターと並列で存在し続けます。 
 

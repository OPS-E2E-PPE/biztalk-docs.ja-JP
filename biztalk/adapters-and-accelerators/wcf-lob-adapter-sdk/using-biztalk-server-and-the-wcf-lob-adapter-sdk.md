---
title: BizTalk Server と WCF LOB Adapter SDK を使用して |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 43ff0357-76e6-42bc-a1f7-0385d9378a5f
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46b06f832fd9ff36f0e274c1599b577bc9ec6010
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989979"
---
# <a name="using-biztalk-server-and-the-wcf-lob-adapter-sdk"></a>BizTalk Server と WCF LOB Adapter SDK の使用
このセクションのリレーションシップに関する情報を格納する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。 このセクションに含まれる情報は各によって提供される 2 つの異なるフレームワークの比較が含まれています、移行のためのヒント、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]カスタム アダプター。  

## <a name="relationship-with-the-sdk-and-biztalk-server"></a>SDK および BizTalk Server との関係
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] SDK とツールと高度なアダプターの操作とデータの動的なセットを格納している基幹業務システムを記述する開発者を有効にするコンポーネントのセットを提供します。 アダプターは、WCF カスタム バインドとして公開され、そのため、WCF バインドを使用するアプリケーションで使用できます。  

 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] メッセージ フローおよびエンタープライズ システムの多様なセットの間で調整できるようにする製品には間の通信[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アダプターを外部メッセージを受け取って処理に適した形式に変換する処理は外部システムと[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。  

 これら 2 つのテクノロジとの交差、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] WCF アダプター。 WCF によって公開されているバインドを使用して操作とで記述されたアダプターによって公開されているデータを消費するため、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。  

 次の図は、内で、BizTalk WCF アダプターと WCF LOB アダプターを使用する方法の概要を提供します。[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ターゲット LOB システムと通信します。  

 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/8dd622c6-ab5e-4cd9-aa86-5176f5c62203.gif "8dd622c6-ab5e-4cd9-aa86-5176f5c62203")  

 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/4f503084-da4f-41cb-92b9-eaea25d1b456.gif "4f503084-da4f-41cb-92b9-eaea25d1b456")  

## <a name="differences-between-the-sdk-and-the-biztalk-server-adapter-framework"></a>SDK と、BizTalk Server アダプター フレームワークの違い

両方の[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]と[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アダプター フレームワークのカスタム アダプターを記述するための SDK の提供がありますはサポート量の大きな違いは、API の観点から提供され、ツールは、再利用性、アダプターの 1 回でも完了しました。  

 2 つのフレームワークの主な違いの一部は、次の表にまとめたものです。  


|     機能      |                                                                   [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]                                                                   |                  [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] アダプター フレームワーク                   |
|------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------|
|       API (API)        | [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)] [!INCLUDE[dotnet451](../../includes/dotnet451-md.md)]アセンブリ、処理、接続の管理、およびメッセージングのメタデータのヘルプのクラスを提供します |                                            COM では、アダプターの操作の基本的なサポートを提供します。                                             |
| アダプターの公開 |                                                            WCF のバインドとして公開WCF バインドを使用できる任意のアプリケーションで使用できます。                                                             | のみ公開される[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]; 他のアプリケーションで再利用します。 |
|      ツール       |                       [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]でのメタデータ ブラウザー [!INCLUDE[btsVStudioNet](../../includes/btsvstudionet-md.md)]                       |                                                                    n/a                                                                     |
|  機能拡張   |                                                                                       [はい] (WCF チャネルの拡張機能) として                                                                                        |                                                                     いいえ                                                                     |

 BizTalk アダプター フレームワークを使用して作成されたアダプターは BizTalk Server 内でのみから使用できるようにします。 その一方で、アダプターに書き込まれた、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]カスタム WCF バインドとして表示されます。 すべて実際には、.NET をされている、サービスを使用する任意のアプリケーションに、これまでの幅が広がりますこのアプリケーションを含む[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 内で WCF ベース アダプターが使用される[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]BizTalk WCF アダプターを使用して、ネイティブの BizTalk アダプターと同時に存在し続けます。 


---
title: ビジュアルで Siebel システムへの接続 Studio を使用してアダプター サービス参照のプラグインの追加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d27121be-6407-4bb6-acb5-37dc8a3785c0
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bdf3ea907ba5905965188d17b3a7493788ef123e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991347"
---
# <a name="connect-to-the-siebel-system-in-visual-studio-using-add-adapter-service-reference-plug-in"></a>ビジュアルで Siebel システムへの接続 Studio を使用して、アダプター サービス参照のプラグインを追加
使用して Siebel システムへの接続に、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] .NET プログラミング ソリューションでは、使用する必要があります、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]します。 このトピックでは、手順を使用する方法には、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
## <a name="connecting-to-a-siebel-system-using-add-adapter-service-reference-plug-in"></a>アダプター サービス参照のプラグインの追加を使用して Siebel システムへの接続  
 使用して Siebel システムへの接続には、次の手順を実行、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
#### <a name="to-connect-to-a-siebel-system"></a>Siebel システムに接続するには  
  
1. 使用して接続する、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] BizTalk ソリューションで。  
  
   1. 使用して BizTalk プロジェクトを作成する[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。  
  
   2. ソリューション エクスプ ローラーでプロジェクトを右クリックし、をクリックし、**アダプター サービス参照の追加**します。 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] が表示されます。  
  
2. **バインディングを選択**ドロップダウン リスト、選択**siebelBinding**、 をクリックし、**構成**します。  
  
3. **アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **ユーザー名**.  
  
4. ユーザー名と Siebel システムへの接続にパスワードを指定します。  
  
5. をクリックして、 **URI プロパティ**タブをクリックし、接続パラメーターの値を指定します。 接続 URI の詳細についてはの[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を参照してください[Siebel システム接続 URI の作成](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)です。  
  
   > [!NOTE]
   >  接続パラメーターに予約済みの文字が含まれている場合、としてを指定する必要がありますのでは、 **URI プロパティ**タブ、つまり、エスケープ文字を使用せずします。 ただし、直接の URI を指定する場合、 **URI の構成**フィールドと接続パラメーターは、予約文字を含めることが、適切なエスケープ文字を使用して接続パラメーターを指定する必要があります。  
  
6. をクリックして、**バインド プロパティ**タブをクリックし、対象と操作に必要な場合、バインドのプロパティの値を指定します。 バインド プロパティの詳細については、[for Siebel のバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)を参照してください。  
  
7. **[OK]** をクリックします。  
  
8. **[接続]** をクリックします。 として、接続の状態が示すように、接続が確立されると、**接続**します。  
  
    次に示します、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]接続が確立された後すぐにします。 グラフィカル ユーザー インターフェイスは変わりません、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
    ![アダプター サービスの使用 ダイアログ ボックスの接続](../../adapters-and-accelerators/adapter-siebel/media/siebel-adpt-lesson1-step3-01-connected.gif "SIEBEL-ADPT-Lesson1-Step3-01-connected")  
  
    [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] Siebel システムで実行できるさまざまな操作を含む別のノードが表示されます。 たとえば、**ビジネス オブジェクト**ノードには、すべてのビジネス オブジェクトと Siebel システムで呼び出すことができるビジネス コンポーネントが含まれています。 同様に、**ビジネス サービス**ノードには、すべてのビジネス サービスに接続されている Siebel システムが含まれています。 これらのノードの詳細については、[メタデータ ノード Id](../../adapters-and-accelerators/adapter-siebel/metadata-node-ids1.md)を参照してください。
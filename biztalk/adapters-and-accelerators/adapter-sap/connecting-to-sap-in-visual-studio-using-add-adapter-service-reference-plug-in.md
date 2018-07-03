---
title: アダプター サービス参照のプラグインの追加を使用して Visual Studio での SAP への接続 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 05116c2f-08a4-495b-a031-d377e7ca33e0
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ced821c84408d519b6ed2ef09d444013a9c6ba82
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971515"
---
# <a name="connecting-to-sap-in-visual-studio-using-add-adapter-service-reference-plug-in"></a>アダプター サービス参照のプラグインの追加を使用して Visual Studio での SAP への接続
SAP システムを使用して接続する、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] .NET プログラミング ソリューションでは、使用する必要があります、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]します。 このトピックでは、手順を使用する方法には、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
## <a name="connecting-to-an-sap-system-using-add-adapter-service-reference-plug-in"></a>接続する SAP システムを使用してアダプター サービス参照のプラグインを追加  
 SAP システムを使用して接続するには、次の手順を実行、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
#### <a name="to-connect-to-an-sap-system"></a>SAP システムに接続するには  
  
1. 使用して接続する、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] BizTalk ソリューションで。  
  
   1. プロジェクトを作成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。  
  
   2. ソリューション エクスプ ローラーでプロジェクトを右クリックし、をクリックし、**アダプター サービス参照の追加**します。 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] が表示されます。  
  
2. **バインディングを選択**ドロップダウン リスト、選択**sapBinding**  をクリック**構成**します。  
  
3. **アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **ユーザー名**ユーザー名と SAP システムへの接続にパスワードを指定します。  
  
   > [!IMPORTANT]
   >  SAP システムに接続する SAP セキュリティで保護されたネットワーク接続 (SNC) ライブラリを使用する場合は、ユーザー名とパスワードを指定しないでください。  
  
4. をクリックして、 **URI プロパティ**タブし、接続パラメーターの値を指定します。 接続 URI の詳細についてはの[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を参照してください[SAP システム接続 URI の作成](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)です。  
  
   > [!IMPORTANT]
   >  SAP システムに接続する SAP SNC ライブラリを使用する場合は、設定、 **UseSnc**接続プロパティを**True**します。  
  
   > [!NOTE]
   >  接続パラメーターに予約済みの文字が含まれている場合、としてを指定する必要がありますのでは、 **URI プロパティ**タブ、つまり、エスケープ文字を使用せずします。 ただし、直接の URI を指定する場合、 **URI の構成**フィールドと接続パラメーターは、予約文字を含めることが、適切なエスケープ文字を使用して接続パラメーターを指定する必要があります。  
  
5. をクリックして、**バインド プロパティ**タブをクリックし、対象と操作に必要な場合、バインドのプロパティの値を指定します。 たとえば、ReceiveIdoc 操作の対象とする場合は、する必要があります設定する、 **ReceiveIdocFormat**プロパティを文字列にバインドします。 バインド プロパティの詳細については、次を参照してください。 [mySAP Business Suite のバインドのプロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)します。  
  
   > [!IMPORTANT]
   >  SAP システムに接続する SAP SNC ライブラリを使用する場合は、設定、 **SncLibrary**と**SncPartnerName**適切な値にします。  
   > 
   >  **SncLibrary**パスと SNC を使用して SAP システムに接続するために必要な Dll のファイル名は、プロパティをバインドします。 これらの Dll、SAP クライアントを使用してコンピューター上に存在する必要がありますと[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]をインストールします。 詳細については、次を参照してください。、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]インストール ガイドで使用可能な\<インストール ガイド\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents します。  
   > 
   >  **SncPartnerName**通信パートナーの SNC 名を受け取るプロパティをバインドします。  
  
6. **[OK]** をクリックします。  
  
7. **[接続]** をクリックします。 接続が確立されると、接続の状態が表示として**接続**します。  
  
    次に示します、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]接続が確立された後すぐにします。 グラフィカル ユーザー インターフェイスは変わりません、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
    ![アダプター サービスの使用 ダイアログ ボックスの接続](../../adapters-and-accelerators/adapter-sap/media/00eb7c9c-3af3-4dad-8c97-2e6ae211b8f0.gif "00eb7c9c-3af3-4dad-8c97-2e6ae211b8f0")  
  
    [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] SAP システムで呼び出すことができるさまざまな成果物を含む別のノードが表示されます。 たとえば、 **RFC**ノードに接続されている SAP システムで使用可能なすべての Rfc が含まれています。 これらのノードの詳細については、次を参照してください。[メタデータ ノード Id](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md)します。  
  
## <a name="see-also"></a>参照  
 [Visual Studio で SAP システムに接続する](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)
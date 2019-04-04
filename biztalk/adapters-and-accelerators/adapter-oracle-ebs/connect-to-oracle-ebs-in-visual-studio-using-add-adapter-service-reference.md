---
title: Add Adapter Service Reference のプラグインを使用して Visual Studio での Oracle E-business Suite への接続 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7fe4d1b7-8201-4816-ae90-020520f29714
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f5ef971b717c721aae9f6f753daaf6fe6eeb30d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976755"
---
# <a name="connect-to-oracle-e-business-suite-in-visual-studio-using-add-adapter-service-reference-plug-in"></a>Add Adapter Service Reference のプラグインを使用して Visual Studio での Oracle E-business Suite への接続します。
Oracle E-business Suite を使用してに接続するため、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] .NET プログラミング ソリューションでは、使用する必要があります、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]します。 このトピックでは、手順を使用する方法には、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  

## <a name="connecting-to-oracle-e-business-suite-using-the-add-adapter-service-reference-plug-in"></a>Oracle E-business Suite を使用して、プラグインのアダプター サービス参照の追加  
 Oracle E-business Suite に接続するのには、次の手順を実行、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  

#### <a name="to-connect-to-oracle-e-business-suite"></a>Oracle E-business Suite に接続するには  

1. 使用して接続する、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]プログラミング ソリューション。  

   1. Visual Studio を使用してプロジェクトを作成します。  

   2. ソリューション エクスプ ローラーでプロジェクトを右クリックし、をクリックし、**アダプター サービス参照の追加**します。 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] が表示されます。  

2. **バインディングを選択**ドロップダウン リスト、選択**oracleEBSBinding**  をクリック**構成**します。  

3. **アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **ユーザー名**ユーザー名と、Oracle E-business Suite に接続するためのパスワードを指定します。  


   |                                                                                           |                                                                                                                                                                                                                                                                                                         |
   |-------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |                                         プロパティ                                          |                                                                                                                                               目的                                                                                                                                                |
   |                     **Oracle データベースの資格情報を使用して接続するには**                      |                                                                          指定、 **ClientCredentialType**プロパティをバインド**データベース**データベース資格情報を指定して**ユーザー名**と**パスワード**テキスト ボックス。                                                                          |
   |                 **Oracle E-business Suite の資格情報を使用して接続するには**                  | 指定、 **ClientCredentialType**プロパティをバインド**EBusiness** for Oracle E-business Suite の資格情報を指定して**ユーザー名**と**パスワード**テキスト ボックス。 する必要がありますの Oracle データベースの資格情報を指定するこの例では、 **OracleUserName**と**OraclePassword**プロパティをバインドします。 |
   | **ClientCredentialType が「データベース」に設定されている場合は、Windows 認証を使用して接続するには**  |                                                                                                         「/」を指定、**ユーザー名**テキスト ボックスと参加解除、**パスワード**空白テキスト ボックス。                                                                                                         |
   | **ClientCredentialType が"EBusiness"に設定されている場合は、Windows 認証を使用して接続するには** |                                       Oracle E-business Suite の資格情報を指定**ユーザー名**と**パスワード**テキスト ボックス。 「/」を指定することも必要があります、 **OracleUserName**バインドのプロパティと参加解除、 **OraclePassword**プロパティは空白をバインドします。                                       |


4. をクリックして、 **URI プロパティ**タブをクリックし、接続パラメーターの値を指定します。 接続 URI の詳細についてはの[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[Oracle E-business Suite 接続 URI の作成](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md)です。  

   > [!NOTE]
   >  接続パラメーターに予約済みの文字が含まれている場合、としてを指定する必要がありますのでは、 **URI プロパティ**タブ、つまり、エスケープ文字を使用せずします。 ただし、直接の URI を指定する場合、 **URI の構成**フィールドと接続パラメーターは、予約文字を含めることが、適切なエスケープ文字を使用して接続パラメーターを指定する必要があります。  

5. をクリックして、**バインド プロパティ**タブをクリックし、対象と操作に必要な場合、バインドのプロパティの値を指定します。 バインド プロパティの詳細については、[Oracle E-business Suite バインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)を参照してください。  

6. **[OK]** をクリックします。  

7. **[接続]** をクリックします。 接続が確立されると、接続の状態が表示として**接続**します。  

    次に示します、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]接続が確立された後すぐにします。 グラフィカル ユーザー インターフェイスが同じ、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  

    ![アダプターのサービス ダイアログ ボックスを使用する](../../adapters-and-accelerators/adapter-oracle-ebs/media/6a2b21ed-0fd2-4874-a6a6-e59a467533f8.gif "6a2b21ed-0fd2-4874-a6a6-e59a467533f8")  

    [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] Oracle E-business Suite と Oracle データベースで実行できるさまざまな操作を含む別のノードが表示されます。 さまざまなノードの下に、メタデータを分類する方法の詳細については、[アダプター メタデータの追加ウィザードを使用して Visual Studio での Oracle E-business Suite への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-ebs-in-visual-studio-using-add-adapter-metadata-wizard.md)を参照してください。  

## <a name="see-also"></a>参照  
 [Visual Studio で Oracle E-business Suite への接続します。](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)   
 [Windows 認証を使用して Oracle E-business Suite への接続します。](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md)
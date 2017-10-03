---
title: "アダプター サービスのアドインを使用して Visual Studio での Oracle E-business Suite への接続 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 62d60216-5065-4048-b073-8618b7685e00
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 441c023d5a8bb83c1998a15cea065b88244209df
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="connect-to-oracle-e-business-suite-in-visual-studio-using-consume-adapter-service-add-in"></a>アダプター サービスのアドインを使用して Visual Studio での Oracle E-business Suite への接続します。
[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]をインストールするときにインストールされている[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]コンピューターにインストールされているすべての WCF カスタム バインドを読み込みます。 WCF ベースを使用して Oracle E-business Suite への接続に[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]BizTalk プロジェクトで使用する必要があります、 **oracleEBSBinding**です。  
  
 このトピックでは、使用する方法の説明、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。  
  
## <a name="connecting-to-oracle-e-business-suite-using-the-consume-adapter-service-add-in"></a>Oracle E-business Suite を使用して、アダプターを使用するアドインでは、サービス  
 Oracle E-business Suite を使用して接続する次の手順を実行、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。  
  
#### <a name="to-connect-to-oracle-e-business-suite"></a>Oracle E-business Suite に接続するには  
  
1.  使用して接続する、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] BizTalk ソリューションで。  
  
    1.  Visual Studio を使用して、BizTalk プロジェクトを作成します。  
  
    2.  ソリューション エクスプ ローラーでプロジェクトを右クリックし、**追加**、クリックして**生成した項目の追加**です。  
  
    3.  **生成した項目の追加** ダイアログ ボックスで、次の操作します。  
  
        |プロパティ|目的|  
        |--------------|----------------|  
        |**カテゴリ**|をクリックして**アダプター サービスの使用**です。|  
        |**[テンプレート]**|をクリックして**アダプター サービスの使用**です。|  
  
    4.  **[追加]**をクリックします。 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] が表示されます。  
  
2.  **バインディングを選択**ドロップダウン リスト、選択**oracleEBSBinding**  をクリック**構成**です。  
  
3.  **アダプターの構成** ダイアログ ボックスをクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **ユーザー名**ユーザー名および Oracle E-business Suite への接続にパスワードを指定します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**Oracle データベースの資格情報を使用して接続するには**|指定、 **ClientCredentialType**にプロパティのバインド**データベース**データベース資格情報を指定して**ユーザー名**と**パスワード**テキスト ボックス。|  
    |**Oracle E-business Suite の資格情報を使用して接続するには**|指定して、 **ClientCredentialType**にプロパティのバインド**EBusiness**用 Oracle E-business Suite の資格情報を指定**ユーザー名**と**パスワード**テキスト ボックス。 この場合は、Oracle データベースの資格情報を指定する必要がありますも**OracleUserName**と**OraclePassword**プロパティをバインドします。|  
    |**ClientCredentialType が"Database"に設定されている場合は、Windows 認証を使用して接続するには**|「/」を指定して、**ユーザー名**テキスト ボックスと参加解除、**パスワード**ボックスは空白です。|  
    |**ClientCredentialType が"EBusiness"に設定されている場合は、Windows 認証を使用して接続するには**|Oracle E-business Suite の資格情報を指定**ユーザー名**と**パスワード**テキスト ボックス。 「/」を指定することも必要があります、 **OracleUserName**バインディング プロパティ、およびのままにして、 **OraclePassword**プロパティは空白をバインドします。|  
  
4.  クリックして、 **URI プロパティ**タブをクリックし、接続パラメーターの値を指定します。 詳細については、接続 URI の[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[Oracle E-business Suite 接続 URI を作成](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md)です。  
  
    > [!NOTE]
    >  接続パラメーターに予約済みの文字が含まれている場合、そのままを指定する必要がありますのでは、 **URI プロパティ** タブでは、エスケープ文字を使用せずします。 ただし、URI で直接指定する場合、 **URI の構成**フィールドと接続パラメーターは、予約文字を含める、適切なエスケープ文字を使用して接続パラメーターを指定する必要があります。  
  
5.  クリックして、**バインド プロパティ**タブをクリックし、対象となる操作で、必要な場合、バインド プロパティの値を指定します。 バインドのプロパティの詳細については、次を参照してください。 [Oracle E-business Suite バインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)です。  
  
6.  **[OK]**をクリックします。  
  
7.  **[接続]**をクリックします。 接続が確立されると、接続状態は表示**接続**です。  
  
     次の図に示しています、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]接続が確立された後にすぐにします。  
  
     ![アダプター サービスのダイアログ ボックスを使用する](../../adapters-and-accelerators/adapter-oracle-ebs/media/6a2b21ed-0fd2-4874-a6a6-e59a467533f8.gif "6a2b21ed-0fd2-4874-a6a6-e59a467533f8")  
  
     [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] Oracle E-business Suite と Oracle データベースで実行できるさまざまな操作を含む別のノードが表示されます。 さまざまなノードの下にメタデータを分類する方法の詳細については、次を参照してください。[アダプター メタデータの追加ウィザードを使用して Visual Studio での Oracle E-business Suite への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-ebs-in-visual-studio-using-add-adapter-metadata-wizard.md)です。  
  
## <a name="see-also"></a>参照  
 [Visual Studio での Oracle E-business Suite への接続します。](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)   
 [Windows 認証を使用して Oracle E-business Suite への接続します。](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md)
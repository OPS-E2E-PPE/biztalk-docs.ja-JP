---
title: アダプター メタデータの追加ウィザードを使用して Visual Studio での Oracle E-business Suite への接続 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4fadc722-0098-457e-a2e2-3e9cc96eab5e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eea516ca2fffb683c4c772ee7719b69edcc0662f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008819"
---
# <a name="connect-to-oracle-e-business-suite-in-visual-studio-using-add-adapter-metadata-wizard"></a>アダプター メタデータの追加ウィザードを使用して Visual Studio での Oracle E-business Suite への接続します。
[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] BizTalk アダプターとしても公開されると、そのため、使用することができます、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]アダプターを使用して Oracle E-business Suite でを実行する操作のスキーマを生成します。  

## <a name="connecting-to-oracle-e-business-suite-using-the-add-adapter-metadata-wizard"></a>Oracle E-business Suite を使用して、アダプター メタデータのウィザードの追加  
 Oracle E-business Suite に接続するのには、次の手順を実行、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。  

#### <a name="to-connect-to-oracle-e-business-suite"></a>Oracle E-business Suite に接続するには  

1. 使用して接続する、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] BizTalk ソリューションで。  

   1. Visual Studio を使用して BizTalk プロジェクトを作成します。  

   2. ソリューション エクスプ ローラーでプロジェクトを右クリックし、[**追加**、] をクリックし、**生成した項目の追加**します。  

   3. **生成した項目の追加** ダイアログ ボックスで、次の操作を行います。  


      |    プロパティ    |           目的            |
      |----------------|---------------------------------|
      | **カテゴリ** |     クリックして**アダプターを追加**します。      |
      | **[テンプレート]**  | クリックして**アダプター メタデータの追加**します。 |


   4. **[追加]** をクリックします。 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] が表示されます。  

   5. [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、 **Wcf-oracleebs**します。 コンピューターを選択します。[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]がインストールされていると、BizTalk データベースの名前。  

      > [!IMPORTANT]
      >  BizTalk で構成された Wcf-oracleebs ポート既にある場合からポートを選択して、**ポート**一覧。  

   6. **[次へ]** をクリックします。  

2. **バインディングを選択**ドロップダウン リスト、選択**oracleEBSBinding**  をクリック**構成**します。  

3. **アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **ユーザー名**ユーザー名と、Oracle E-business Suite に接続するためのパスワードを指定します。  


   |                                                                                           |                                                                                                                                                                                                                                                                                                         |
   |-------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |                                         プロパティ                                          |                                                                                                                                               目的                                                                                                                                                |
   |                     **Oracle データベースの資格情報を使用して接続するには**                      |                                                                          指定、 **ClientCredentialType**プロパティをバインド**データベース**データベース資格情報を指定して**ユーザー名**と**パスワード**テキスト ボックス。                                                                          |
   |                 **Oracle E-business Suite の資格情報を使用して接続するには**                  | 指定、 **ClientCredentialType**プロパティをバインド**EBusiness** for Oracle E-business Suite の資格情報を指定して**ユーザー名**と**パスワード**テキスト ボックス。 する必要がありますの Oracle データベースの資格情報を指定するこの例では、 **OracleUserName**と**OraclePassword**プロパティをバインドします。 |
   | **ClientCredentialType が「データベース」に設定されている場合は、Windows 認証を使用して接続するには**  |                                                                                                         「/」を指定、**ユーザー名**テキスト ボックスと参加解除、**パスワード**空白テキスト ボックス。                                                                                                         |
   | **ClientCredentialType が"EBusiness"に設定されている場合は、Windows 認証を使用して接続するには** |                                       Oracle E-business Suite の資格情報を指定**ユーザー名**と**パスワード**テキスト ボックス。 「/」を指定することも必要があります、 **OracleUserName**バインドのプロパティと参加解除、 **OraclePassword**プロパティは空白をバインドします。                                       |


4. をクリックして、 **URI プロパティ**タブをクリックし、接続パラメーターの値を指定します。 接続 URI の詳細についてはの[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[Oracle E-business Suite 接続 URI の作成](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md))。  

   > [!NOTE]
   >  接続パラメーターに予約済みの文字が含まれている場合、としてを指定する必要がありますのでは、 **URI プロパティ**タブ、つまり、エスケープ文字を使用せずします。 ただし、直接の URI を指定する場合、 **URI の構成**フィールドと接続パラメーターは、予約文字を含めることが、適切なエスケープ文字を使用して接続パラメーターを指定する必要があります。  

5. をクリックして、**バインド プロパティ**タブをクリックし、対象と操作に必要な場合、バインドのプロパティの値を指定します。 バインド プロパティの詳細については、次を参照してください。 [Oracle E-business Suite バインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)します。  

   > [!NOTE]
   >  使用してメタデータを生成している場合[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]と既存の Wcf-oracleebs 送信ポートを選択した、バインドのプロパティを指定する必要はありません。 バインドのプロパティは、送信ポートの構成から取得されます。 ただし、存在する場合に、デザイン時に必要なバインドのプロパティを指定することができます。 このような場合、メタデータの生成中にプロパティをバインドするための新しい値をデザイン時に使用されます。 ただし、実行時に送信ポートの構成でバインドのプロパティに指定された値を適用できるになります。  

6. **[OK]** をクリックします。  

7. **[接続]** をクリックします。 接続が確立されると、接続の状態が表示として**接続**します。  

    次に示します、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]接続が確立された後すぐにします。  

    ![アダプターのサービス ダイアログ ボックスを使用する](../../adapters-and-accelerators/adapter-oracle-ebs/media/6a2b21ed-0fd2-4874-a6a6-e59a467533f8.gif "6a2b21ed-0fd2-4874-a6a6-e59a467533f8")  

    [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] Oracle E-business Suite と Oracle データベースで実行できるさまざまな操作を含む別のノードが表示されます。 さまざまなノードの下に、メタデータを分類する方法の詳細については、次を参照してください。[アダプター メタデータの追加ウィザードを使用して Visual Studio での Oracle E-business Suite への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-ebs-in-visual-studio-using-add-adapter-metadata-wizard.md)します。  

## <a name="see-also"></a>参照  
 [Visual Studio で Oracle E-business Suite への接続します。](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)   
 [Windows 認証を使用して Oracle E-business Suite への接続します。](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md)
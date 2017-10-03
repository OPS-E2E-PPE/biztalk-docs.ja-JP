---
title: "手順 2: が作成および展開サンプル X12 スキーマ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d5862168-6621-40ab-8c97-3f317530d34e
caps.latest.revision: "31"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe4f937af910ceef1ed461e25ea3c62cad5cbc29
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-create-and-deploy-the-sample-x12-schema"></a>手順 2: が作成および展開サンプル X12 スキーマ
![手順 11 の 2](../core/media/tut-step2-of-11.gif "Tut_Step2_of_11")  
  
 このステップでは、AS2 トランスポートを経由した受信 EDI X12 インターチェンジを処理するために必要な、サンプル EDI X12 スキーマを提供するプロジェクトをビルドし、展開します。 このチュートリアルでは、スキーマ X12_00401_864.xsd を使用します。 AS2 チュートリアルに付属のプロジェクトを変更する必要はありません。実行する必要があるのはビルドだけです。  
  
> [!NOTE]
>  このチュートリアルで使用するスキーマ ファイル X12_00401_864.xsd は、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Schemas フォルダー内にあります。 このスキーマ ファイルは、このステップでビルドと展開を行う対象の Schemas プロジェクトに既に追加されています。 このスキーマは、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI フォルダーにある MicrosoftEdiXsdTemplates.exe を実行してコンピューターにダウンロードされる X12_00401_864.xsd ファイルとは異なります。 このチュートリアルを実行するには、Schemas.btproj に追加されている X12_00401_864.xsd ファイルを使用する必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-create-and-deploy-the-sample-x12-schema"></a>サンプル X12 スキーマを作成して展開するには  
  
1.  開始**Microsoft Visual Studio**を管理者として。  
  
2.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、ソリューション [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Schemas\Schemas.sln を開きます。  
  
    > [!NOTE]
    >  このトピックは、EDI スキーマ、パイプライン、およびオーケストレーションを含む BizTalk EDI アプリケーションに別のアプリケーションから参照を既に追加していることを前提としています。 いない場合を参照してください。[を BizTalk Server EDI アプリケーションへの参照を追加する方法](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)です。  
  
3.  Schemas プロジェクトを右クリックし、をクリックして**プロパティ**です。 クリックして、**署名**プロジェクト デザイナーのタブです。 チェック、**アセンブリに署名** チェック ボックスの**強力なキー名ファイルを選択して**を選択**\<新規作成 ...> >**入力と`Schemas.snk`です。 クリア**キーファイルをパスワードで保護する**順にクリック**OK**です。 プロジェクトのプロパティのダイアログ ボックスを閉じ、変更を保存します。  
  
4.  Schemas.btproj をビルドおよび展開します。  
  
## <a name="next-steps"></a>次の手順  
 説明に従って、組織 (Contoso) のパーティとビジネス プロファイルを構成する[手順 3: 組織のパーティとビジネス プロファイルを構成する](../core/step-3-configure-a-party-and-business-profile-for-your-organization2.md)です。  
  
## <a name="see-also"></a>参照  
 [EDI ドキュメント スキーマ](../core/edi-document-schemas.md)
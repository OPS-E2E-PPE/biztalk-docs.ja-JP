---
title: Oracle ユーザー定義 Types2 のサポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d4b9980-fa5b-4340-a62f-e4a4f98603dc
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e9bd33864523f40255cbf0dcf993fd916f02270
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973267"
---
# <a name="support-for-oracle-user-defined-types"></a>Oracle ユーザー定義型のサポート
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] Oracle User-Defined 型 (Udt) が含まれている Oracle E-business Suite と基になるデータベース内の成果物に対する操作の実行をサポートします。 Udt は、次の成果物で使用できます。  
  
-   インターフェイス テーブルと UDT 列を含むインターフェイス ビュー。  
  
-   データベース テーブルと UDT 列を含むビュー。  
  
-   パッケージ、ストアド プロシージャ、および UDT パラメーターを含む関数。  
  
## <a name="what-is-an-oracle-udt"></a>Oracle UDT とは何ですか。  
 Oracle の Udt のアプリケーション間で共有できる"single"オブジェクトとしての複雑なエンティティを表すのに役立ちます。 たとえば、行うことが"Customers"や"Sales Orders"などのモデルの実際のエンティティとして Oracle データベース内のオブジェクト。 Oracle Udt は、Oracle データベースで定義され、次の 2 種類の。  
  
- オブジェクトの種類。 たとえば、Oracle のオブジェクトです。  
  
- コレクション型。 たとえば、入れ子になったテーブルの種類または VARRAY します。  
  
  Oracle の UDT の名前は大文字小文字が区別し、次のように指定する必要があります。 [SCHEMA_NAME]。[UDT_NAME]。  
  
## <a name="how-does-the-adapter-support-oracle-udt"></a>アダプターが、Oracle UDT をサポートする方法  
 ODP.NET では、.NET 型 (カスタム型) として Oracle データベースで定義されている Oracle Udt を表すことで Udt をサポートしています。 カスタム型は、.NET メンバーに、Oracle の UDT の属性または要素の間のマッピングを定義します。 カスタム型は、.NET クラスまたは構造体を指定でき、オブジェクトの Oracle または Oracle コレクションのいずれかを表すことができます。  という事実に起因する、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ODP.NET を使用して、Oracle データベースに接続は、Oracle の Udt のサポートを継承します。  
  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ODP.NET を使用して、データベース、Oracle の UDT を .NET カスタム型をマップするカスタム型マッピングを指定します。 カスタム型マッピングを指定する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]カスタム型のファクトリを使用します。 そのため、Oracle、UDT を使用するにはアセンブリ (.dll ファイル) が必要なカスタム型のファクトリを定義します。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle の UDT を含む成果物/操作のメタデータを生成するときに、カスタム型のファクトリのアセンブリを生成することができます。  
  
> [!NOTE]
>  アダプターは、Oracle の Udt をサポートするために、ODP.NET によって使用されるクラスに基づく Oracle Udt のアセンブリを生成します。 ODP.NET で Oracle Udt をサポートする方法の詳細については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=140697](http://go.microsoft.com/fwlink/?LinkId=140697)します。  
  
 デザイン時に Oracle Udt を使用するためのアセンブリ ファイルを生成し、後で、実行時に、使用して、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]バインドのプロパティを公開します。  
  
- **GeneratedUserTypesAssemblyFilePath** (デザイン時)  
  
- **GeneratedUserTypesAssemblyKeyFilePath** (デザイン時)  
  
- **UserAssembliesLoadPath** (実行時)  
  
  これらのバインドのプロパティについては、次を参照してください。[については、BizTalk Adapter for Oracle E-business Suite バインド プロパティを読み取る](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)します。  
  
## <a name="performing-operations-on-artifacts-containing-oracle-udts"></a>Oracle の Udt を含む成果物の操作を実行します。  
 使用して Udt を含む成果物の操作を実行する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]デザイン時に、次を実行して、時間を実行する必要があります。  
  
### <a name="design-time"></a>デザイン時  
 Visual Studio での操作のスキーマの生成中に次の手順を実行する必要があります。  
  
1. Oracle E-business Suite への接続、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 これについては、次を参照してください。 [Visual Studio での Oracle E-business Suite への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)します。  
  
2. 、接続中に、**バインドのプロパティ**のタブ、**アダプターの構成** ダイアログ ボックスで、適切な値を指定、 **GeneratedUserTypesAssemblyFilePath****GeneratedUserTypesAssemblyKeyFilePath**プロパティをバインドします。 これらのバインドのプロパティについては、次を参照してください。[については、BizTalk Adapter for Oracle E-business Suite バインド プロパティを読み取る](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)します。  
  
3. Visual Studio での Oracle E-business Suite に接続しているときに、Oracle、UDT を含む必要な成果物を参照します。 成果物をブラウズする方法の詳細については、次を参照してください。[参照、検索、および取得操作のメタデータの Oracle E-business](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)します。  
  
4. 必須のアイテムを選択し、クリックして**OK**します。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]選択したアイテムで Oracle UDT のアセンブリ (.dll ファイル) と共に選択した操作のメタデータを生成します。 指定した場所にアセンブリが作成されて、 **GeneratedUserTypesAssemblyFilePath**プロパティをバインドします。  
  
5. 構築して、プロジェクトの配置手順の残りの部分を続行します。  
  
### <a name="run-time"></a>実行時間  
 Oracle の Udt の操作を実行するアダプターのクライアントでは、これらの手順を実行する必要があります。  
  
 **BizTalk server**  
  
- 手順 4. で「デザイン時」グローバル アセンブリ キャッシュ (GAC) に、コンピューター上で作成された Oracle UDT アセンブリを手動で追加します。 BizTalk Server のインストール場所の Oracle UDT アセンブリを手動でコピーすることができます。 BizTalk server では、通常、これは\<インストール ドライブ\>: \Program Files\Microsoft BizTalk Server です。  
  
- 構成するときに、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Wcf-custom または Wcf-oracleebs をポートで、**バインド**] タブの [Oracle UDT アセンブリの場所を指定の**UserAssembliesLoadPath**プロパティをバインドします。 このバインドのプロパティについては、次を参照してください。[については、BizTalk Adapter for Oracle E-business Suite バインド プロパティを読み取る](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)します。  
  
  **Visual Studio で**  
  
- 手順 4. で「デザイン時」グローバル アセンブリ キャッシュ (GAC) に、コンピューター上で作成された Oracle UDT アセンブリを手動で追加します。 または、通常、プロジェクトの \bin\Debug フォルダーの下にはプロジェクトの実行可能ファイルと同じ場所に Oracle UDT アセンブリを手動でコピーすることができます。  
  
- Oracle の UDT のアセンブリの場所を指定、 **UserAssembliesLoadPath**プロパティをバインドします。 このバインドのプロパティについては、次を参照してください。[については、BizTalk Adapter for Oracle E-business Suite バインド プロパティを読み取る](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)します。  
  
## <a name="see-also"></a>参照  
 [どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)
---
title: Oracle データベースでの Oracle ユーザー定義型のサポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 68edf0f2-a798-4096-86ca-85d2cfa9088a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9bf839d214d0877ea51430cd0c4a7784ebfa3cc8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007059"
---
# <a name="support-for-oracle-user-defined-types-in-oracle-database"></a>Oracle データベースでの Oracle ユーザー定義型のサポート
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] Oracle User-Defined 型 (Udt) が含まれている Oracle データベースでの成果物に対する操作の実行をサポートします。 Udt は、次の成果物で使用できます。  
  
-   テーブルと UDT 列を含むビュー。  
  
-   パッケージ、ストアド プロシージャ、および UDT パラメーターを含む関数。  
  
## <a name="what-is-an-oracle-udt"></a>Oracle UDT とは何ですか。  
 Oracle の Udt のアプリケーション間で共有できる"single"オブジェクトとしての複雑なエンティティを表すのに役立ちます。 たとえば、行うことが"Customers"や"Sales Orders"などのモデルの実際のエンティティとして Oracle データベース内のオブジェクト。 Oracle Udt は、Oracle データベースで定義され、次の 2 種類の。  
  
- オブジェクトの種類。 たとえば、Oracle のオブジェクトです。  
  
- コレクション型。 たとえば、入れ子になったテーブルの種類または VARRAY します。  
  
  Oracle の UDT の名前は大文字小文字が区別し、次のように指定する必要があります。 [SCHEMA_NAME]。[UDT_NAME]。  
  
## <a name="how-does-the-adapter-support-oracle-udt"></a>アダプターが、Oracle UDT をサポートする方法  
 ODP.NET では、.NET 型 (カスタム型) として Oracle データベースで定義されている Oracle Udt を表すことで Udt をサポートしています。 カスタム型は、.NET メンバーに、Oracle の UDT の属性または要素の間のマッピングを定義します。 カスタム型は、.NET クラスまたは構造体を指定でき、オブジェクトの Oracle または Oracle コレクションのいずれかを表すことができます。  という事実に起因する、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] ODP.NET を使用して、Oracle データベースに接続は、Oracle の Udt のサポートを継承します。  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] ODP.NET を使用して、データベース、Oracle の UDT を .NET カスタム型をマップするカスタム型マッピングを指定します。 カスタム型マッピングを指定する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]カスタム型のファクトリを使用します。 そのため、Oracle、UDT を使用するにはアセンブリ (.dll ファイル) が必要なカスタム型のファクトリを定義します。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle の UDT を含む成果物/操作のメタデータを生成するときに、カスタム型のファクトリのアセンブリを生成することができます。  
  
> [!NOTE]
>  アダプターは、Oracle の Udt をサポートするために、ODP.NET によって使用されるクラスに基づく Oracle Udt のアセンブリを生成します。 ODP.NET で Oracle Udt をサポートする方法の詳細については、[ http://go.microsoft.com/fwlink/?LinkId=140697](http://go.microsoft.com/fwlink/?LinkId=140697)を参照してください。  
  
 デザイン時に Oracle Udt を使用するためのアセンブリ ファイルを生成し、後で、実行時に、使用して、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]バインドのプロパティを公開します。  
  
- **GeneratedUserTypesAssemblyFilePath** (デザイン時)  
  
- **GeneratedUserTypesAssemblyKeyFilePath** (デザイン時)  
  
- **UserAssembliesLoadPath** (実行時)  
  
  これらのバインドのプロパティについては、[for Oracle Database バインド プロパティを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)を参照してください。  
  
## <a name="performing-operations-on-artifacts-containing-oracle-udts"></a>Oracle の Udt を含む成果物の操作を実行します。  
 使用して Udt を含む成果物の操作を実行する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]デザイン時に、次を実行して、時間を実行する必要があります。  
  
### <a name="design-time"></a>デザイン時  
 Visual Studio での操作のスキーマの生成中に次の手順を実行する必要があります。  
  
1. Oracle データベースに接続する、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 これについては、[Consume Adapter Service を使用して Visual Studio での Oracle データベースへの接続](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio-using-the-consume-adapter-service.md)を参照してください。  
  
2. 、接続中に、**バインドのプロパティ**のタブ、**アダプターの構成** ダイアログ ボックスで、適切な値を指定、 **GeneratedUserTypesAssemblyFilePath****GeneratedUserTypesAssemblyKeyFilePath**プロパティをバインドします。 これらのバインドのプロパティについては、[for Oracle Database バインド プロパティを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)を参照してください。  
  
3. Visual Studio で Oracle データベースに接続しているときに、Oracle、UDT を含む必要な成果物を参照します。 成果物をブラウズする方法の詳細については、[参照、検索、および Oracle データベース操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-database/browse-search-and-get-metadata-for-oracle-database-operations.md)を参照してください。  
  
4. 必須のアイテムを選択し、クリックして**OK**します。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]選択したアイテムで Oracle UDT のアセンブリ (.dll ファイル) と共に選択した操作のメタデータを生成します。 指定した場所にアセンブリが作成されて、 **GeneratedUserTypesAssemblyFilePath**プロパティをバインドします。  
  
5. 構築して、プロジェクトの配置手順の残りの部分を続行します。  
  
### <a name="run-time"></a>実行時間  
 Oracle の Udt の操作を実行するアダプターのクライアントでは、これらの手順を実行する必要があります。  
  
 **BizTalk server**  
  
- 手順 4. で「デザイン時」グローバル アセンブリ キャッシュ (GAC) に、コンピューター上で作成された Oracle UDT アセンブリを手動で追加します。 BizTalk Server のインストール場所の Oracle UDT アセンブリを手動でコピーすることができます。 BizTalk server では、通常、これは\<インストール ドライブ\>: \Program Files\Microsoft BizTalk Server です。  
  
- 構成するときに、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Wcf-custom または Wcf-oracledb をポートで、**バインド**] タブの [Oracle UDT アセンブリの場所を指定の**UserAssembliesLoadPath**プロパティをバインドします。 このバインドのプロパティについては、[for Oracle Database バインド プロパティを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)を参照してください。  
  
  **Visual Studio で**  
  
- 手順 4. で「デザイン時」グローバル アセンブリ キャッシュ (GAC) に、コンピューター上で作成された Oracle UDT アセンブリを手動で追加します。 または、通常、プロジェクトの \bin\Debug フォルダーの下にはプロジェクトの実行可能ファイルと同じ場所に Oracle UDT アセンブリを手動でコピーすることができます。  
  
- Oracle の UDT のアセンブリの場所を指定、 **UserAssembliesLoadPath**プロパティをバインドします。 このバインドのプロパティについては、[for Oracle Database バインド プロパティを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)を参照してください。  
  
## <a name="see-also"></a>参照  
 [どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)
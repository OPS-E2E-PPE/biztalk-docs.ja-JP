---
title: "Oracle データベースの Oracle ユーザー定義型のサポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 68edf0f2-a798-4096-86ca-85d2cfa9088a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3de61b0659e06ebbf7b95f0b4adcad210c5c986e
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="support-for-oracle-user-defined-types-in-oracle-database"></a>Oracle データベースの Oracle ユーザー定義型のサポート
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] Oracle User-Defined 型 (Udt) を含む Oracle データベースでの成果物に対する操作の実行をサポートします。 Udt は、次の成果物になくてもかまいません。  
  
-   テーブルと UDT 列を含むビュー。  
  
-   パッケージ、ストアド プロシージャ、および UDT パラメーターを含む関数。  
  
## <a name="what-is-an-oracle-udt"></a>Oracle UDT とは何ですか。  
 Oracle Udt は、アプリケーション間で共有できる「単一」のオブジェクトとしての複雑なエンティティを表すときに役立ちます。 たとえば、可能であれば"Customers"または"Sales Orders"などの実際のエンティティをモデルに Oracle データベース内のオブジェクトとして。 Oracle データベースで oracle Udt が定義されているし、次の 2 種類の。  
  
-   オブジェクトの種類。 たとえば、Oracle オブジェクトです。  
  
-   コレクション型。 たとえば、入れ子になったテーブルの種類または VARRAY します。  
  
 Oracle UDT の名前は大文字と小文字が区別し、次のように指定する必要があります。 [SCHEMA_NAME] です。[UDT_NAME] です。  
  
## <a name="how-does-the-adapter-support-oracle-udt"></a>アダプターが Oracle UDT をサポートする方法  
 ODP.NET では、.NET 型 (カスタム型) として、Oracle データベースで定義されている Oracle Udt を表すことで Udt をサポートしています。 カスタム型は、.NET メンバーに Oracle UDT の属性または要素の間のマッピングを定義します。 カスタム型は、.NET クラスまたは構造体を指定でき、Oracle オブジェクトまたは Oracle コレクションのいずれかを表すことができます。  ファクトに起因する、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] ODP.NET を使用して Oracle データベースに接続 Oracle Udt のサポートを継承します。  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] ODP.NET を使用して .NET カスタム型をデータベースに、Oracle UDT にマップするカスタム型マッピングを指定します。 カスタム型マッピングを指定する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]カスタムの型ファクトリを使用します。 そのため、Oracle UDT を使用するためにアセンブリ (.dll ファイル) が必要なカスタムの型ファクトリを定義します。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle UDT を含む成果物/操作のメタデータを生成するときにカスタムの型ファクトリのアセンブリを生成することができます。  
  
> [!NOTE]
>  アダプターは、Oracle の Udt をサポートするために、ODP.NET で使用されるクラスに基づく Oracle Udt のアセンブリを生成します。 ODP.NET で Oracle Udt をサポートする方法の詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=140697](http://go.microsoft.com/fwlink/?LinkId=140697)です。  
  
 デザイン時に Oracle Udt を使用するためのアセンブリ ファイルを生成して後で、実行時に、使用できるように、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]バインドのプロパティを公開します。  
  
-   **GeneratedUserTypesAssemblyFilePath** (デザイン時)  
  
-   **GeneratedUserTypesAssemblyKeyFilePath** (デザイン時)  
  
-   **UserAssembliesLoadPath** (実行時)  
  
 これらのバインディング プロパティについては、次を参照してください。 [Oracle データベースのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)です。  
  
## <a name="performing-operations-on-artifacts-containing-oracle-udts"></a>Oracle の Udt を含む成果物の操作を実行します。  
 使用して Udt を含む成果物の操作を実行する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]デザイン時に次の操作を時間を実行してください。  
  
### <a name="design-time"></a>デザイン時  
 Visual Studio での操作のスキーマの生成中に次の手順を実行する必要があります。  
  
1.  Oracle データベースへの接続、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。 これについては、次を参照してください。[アダプター サービスの使用を使用して Visual Studio での Oracle データベースへの接続](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio-using-the-consume-adapter-service.md)です。  
  
2.  、接続中に、**バインド プロパティ**のタブ、**アダプターの構成** ダイアログ ボックスで、適切な値を指定、 **GeneratedUserTypesAssemblyFilePath**および**GeneratedUserTypesAssemblyKeyFilePath**プロパティをバインドします。 これらのバインディング プロパティについては、次を参照してください。 [Oracle データベースのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)です。  
  
3.  Visual Studio での Oracle database に接続しているときに、Oracle UDT を含む必要なアイテムを参照します。 成果物を参照する方法については、次を参照してください。[参照、検索、および Oracle データベースの操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-database/browse-search-and-get-metadata-for-oracle-database-operations.md)です。  
  
4.  必要な成果物を選択し、クリックして**OK**です。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]選択したアイテムで Oracle UDT のアセンブリ (.dll ファイル) と、選択した操作のメタデータを生成します。 指定した場所にアセンブリが作成、 **GeneratedUserTypesAssemblyFilePath**プロパティをバインドします。  
  
5.  構築し、プロジェクトを配置するための手順の残りの部分を続行します。  
  
### <a name="run-time"></a>実行時間  
 Oracle Udt に対する操作を実行するアダプターのクライアントでは、これらの手順を実行する必要があります。  
  
 **BizTalk Server で**  
  
-   手順 4. で「デザイン時」グローバル アセンブリ キャッシュ (GAC) に、コンピューター上で作成された Oracle UDT アセンブリを手動で追加します。 BizTalk Server のインストール場所の下にある Oracle UDT アセンブリを手動でコピーすることができます。 BizTalk server では、通常、これは\<インストール ドライブ\>: \Program Files\Microsoft BizTalk Server です。  
  
-   構成中に、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Wcf-custom または Wcf-oracledb をポートで、**バインディング**] タブの [Oracle UDT アセンブリの場所を指定の**UserAssembliesLoadPath**プロパティをバインドします。 このバインディングのプロパティについては、次を参照してください。 [Oracle データベースのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)です。  
  
 **Visual Studio で**  
  
-   手順 4. で「デザイン時」グローバル アセンブリ キャッシュ (GAC) に、コンピューター上で作成された Oracle UDT アセンブリを手動で追加します。 また、通常は、プロジェクトの \bin\Debug フォルダーの下にあるプロジェクトの実行可能ファイルと同じ場所に Oracle UDT アセンブリを手動でコピーすることができます。  
  
-   Oracle の UDT のアセンブリの場所を指定する、 **UserAssembliesLoadPath**プロパティをバインドします。 このバインディングのプロパティについては、次を参照してください。 [Oracle データベースのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)です。  
  
## <a name="see-also"></a>参照  
 [どのような操作をアダプターであるを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)
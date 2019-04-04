---
title: アプリケーションのコンテキストの設定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e9697155-70c0-4173-80d2-d02d103c397b
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a512f2b3e198d496390bdc462af073bf05c1668
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004235"
---
# <a name="set-application-context"></a>アプリケーションのコンテキストの設定
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]、それらの操作を実行する前に、アプリケーション コンテキストの設定は必須です (インターフェイス テーブル、インターフェイス ビュー、同時実行プログラム、および要求のセット) によって Oracle E-business Suite の成果物。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]アプリケーション コンテキストを設定するまで、これらの成果物の操作を実行することはできません。 ただしの基になる Oracle データベース アイテム、そのユーザーの責任ですか、アプリケーションのコンテキストを設定するかどうか。  
  
## <a name="what-is-application-context"></a>アプリケーションのコンテキストとは  
 アプリケーションのコンテキストでは、一連のユーザー設定と、アイテムに対するアクセス制御を実装する Oracle E-business Suite 内のアイテムに関連付けられている要素です。 アプリケーションのコンテキストでは、次の要素で構成されます。  
  
- **ユーザー名**: Oracle E-business Suite に接続できるユーザー。  
  
- **責任**: 責任はユーザーがこれらのデータと、組織では、そのロールに適切な関数にアクセスできる Oracle E-business Suite でアクセス レベル。 責任は、単位、書籍、および windows、関数、およびその他の責任の制限の一覧の動作の特定のアプリケーションへのアクセスを許可できます。 により、ユーザーの責任の割り当て、許可/アクセスを制限できます Oracle E-business Suite 内のユーザー。  
  
- **組織 ID**: Oracle E-business Suite は、複数の組織の構成の設定をサポートします。 複数の異なる組織は、値、組織 ID では、これらの組織に関する情報を格納する Oracle E-business Suite 内のテーブルの Org_ID 列で一意に識別されます。 により、組織の責任を割り当てまたは組織を明示的に選択すると、許可/アクセスを制限できますユーザーの組織にします。  
  
  役割の詳細については、複数の組織、および Oracle E-business suite で組織 ID を検索して、 [Oracle ヘルプ センター](http://docs.oracle.com)します。  
  
## <a name="setting-application-context"></a>アプリケーション コンテキストの設定  
 として、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite の成果物の確立またはアダプターで初期化されていないのは、Oracle E-business Suite、アプリケーションのコンテキストで基になるデータベースに接続します。 初期化またはアプリケーションのコンテキストでこれらの成果物を設定することができます、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]次のいずれかを使用しています。  
  
- **バインドのプロパティ**:[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]アプリケーション コンテキストを設定するための次のバインド プロパティを公開します: **OracleEBSOrganizationId**、 **OracleUserName**、 **OraclePassword**、 **OracleEBSResponsibilityKey**、 **OracleEBSResponsibilityName**、および**ApplicationShortName**します。 さまざまなアイテムのコンテキストをアプリケーション設定にこれらすべてのバインド プロパティの値を指定する必要はありません。 成果物のアプリケーション コンテキストの設定に必要なバインドのプロパティについては、[設定アプリケーション コンテキストのさまざまなアイテムのプロパティをバインド](#Binding)このトピックで後述を参照してください。  
  
- **メッセージ コンテキスト プロパティ**:[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]アプリケーション コンテキストを設定するための次のメッセージ コンテキスト プロパティを公開します: **ApplicationShortName**、**組織 Id**、 **ResponsibilityKey**、および**ResponsibilityName**します。 ユーザー名とパスワードを指定するためには、バインドのプロパティを使用する必要があります。 メッセージ コンテキスト プロパティを使用してアプリケーションのコンテキストを設定する方法については、[アプリケーション コンテキストを使用してメッセージのコンテキスト プロパティを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-application-context-using-message-context-properties-in-oracle-ebs.md)を参照してください。  
  
> [!IMPORTANT]
>  指定された値、 **OracleEBSResponsibilityKey**の値を上書きするプロパティのバインド、 **OracleEBSResponsibilityName**プロパティをバインドします。 同様に、指定された値、 **ResponsibilityKey**メッセージ コンテキスト プロパティに指定された値のオーバーライド、 **ResponsibilityName**メッセージ コンテキスト プロパティ。  
  
### <a name="precedence-order-binding-properties-vs-message-context-properties"></a>優先順位 (メッセージ コンテキスト プロパティとバインドのプロパティ)  
 バインドのプロパティとメッセージ コンテキスト プロパティの両方を使用して、アプリケーションのコンテキストを設定すると、メッセージ コンテキスト プロパティに指定された値が優先され、バインドのプロパティに指定された値を上書きします。 などとしてメッセージ コンテキスト プロパティとバインドのプロパティとして、他のアプリケーションの短い名前を指定した場合のみアプリケーションの短い名前の値は、メッセージ コンテキスト プロパティから取得され、残りの部分は、関連するバインドから取得されます。プロパティ。  
  
 **短い名前のアプリケーションの優先順位**  
  
 アプリケーションのコンテキストを設定中には、アプリケーションの短い名前は、次の優先順位 (最下位に最も高い) で使用されます。  
  
- 指定されたアプリケーションの短い名前、 **ApplicationShortName**メッセージ コンテキスト プロパティ。  
  
- (インターフェイス テーブル、インターフェイス ビュー、同時実行プログラム、および要求セットの場合のみ) の SOAP アクションで指定されたアプリケーション短い名前。  
  
- 指定されたアプリケーションの短い名前、 **ApplicationShortName**プロパティをバインドします。  
  
  ただし、インターフェイス テーブル、インターフェイス ビュー、同時実行プログラム、および要求セットの場合、この優先順位がのみ適用されるアプリケーションのコンテキストを設定中にします。 インターフェイス テーブル、ビューのインターフェイスを識別するには、同時実行プログラム、および要求設定すると、SOAP アクションで短い名前を使用するアプリケーション。  
  
  **責任のキーと役割名の優先順位**  
  
  アプリケーションのコンテキストを設定中に、責任のキーと責任の名前は、次の優先順位 (最下位に最も高い) で使用されます。  
  
- 指定する責任キー、 **ResponsibilityKey**メッセージ コンテキスト プロパティ。  
  
- 指定された役割名、 **ResponsibilityName**メッセージ コンテキスト プロパティ。  
  
- 指定する責任キー、 **OracleEBSResponsibilityKey**プロパティをバインドします。  
  
- 指定された役割名、 **OracleEBSResponsibilityName**プロパティをバインドします。  
  
> [!TIP]
>  **アプリケーションのコンテキストを設定するプロパティをバインド経由でメッセージ コンテキスト プロパティを使用する理由** バインドのプロパティを使用して、アプリケーションのコンテキストを設定すると、WCF カスタムは用、Oracle E-business アダプターは、特定の組織の ID、責任、およびバインドのプロパティに指定したアプリケーションに対してのみ使用できますをポートに送信します。 反対に、メッセージ コンテキスト プロパティを使用する場合は、「汎用」Wcf-custom 送信ポートを構成し、メッセージ レベルで、アプリケーションのコンテキストを設定します。  
  
### <a name="setting-application-context-for-interface-tables-interface-views-concurrent-programs-and-request-sets-mandatory"></a>インターフェイス テーブル、インターフェイス ビュー、同時実行プログラム、および要求セット (必須) のアプリケーション コンテキストの設定  
 インターフェイス テーブル、インターフェイス ビュー、同時実行プログラムは、操作を実行する前に、アプリケーションのコンテキストを設定する必要があり、要求の設定[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。 これを行うには、バインドのプロパティまたは以前に指定したメッセージ コンテキスト プロパティの適切な値を指定があります。  
  
> [!IMPORTANT]
>  インターフェイス テーブルでの操作を実行することはできません、インターフェイス ビュー、同時実行プログラム、および要求コンテキストのプロパティの必要なバインドのプロパティまたはメッセージの適切な値を設定しない限りを設定します。  
  
### <a name="setting-application-context-for-plsql-apis-procedures-functions-tables-and-views"></a>PL/SQL Api、プロシージャ、関数、テーブル、およびビューのアプリケーション コンテキストの設定  
  
- **PL/SQL Api**: [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle データベースと Oracle E-business Suite アプリケーションに関連付けられている PL/SQL Api を公開します。 Oracle データベースに関連付けられた PL/SQL Api のアプリケーションのコンテキストを設定する省略可能ですが、Oracle E-business Suite アプリケーションに関連付けられている PL/SQL Api のアプリケーションのコンテキストを設定するのには必須では。  
  
- **プロシージャおよび関数**: Oracle データベースでプロシージャおよび関数での操作を実行するアプリケーションのコンテキストを設定する必要はありません。  
  
- **テーブルとビュー**: Oracle データベースでテーブルとビューで操作を実行するアプリケーションのコンテキストを設定する必要はありません。 ただし、カスタムの Oracle E-business Suite アプリケーションでは、ユーザーが可能性があります。 またはベース データベース テーブルにはインターフェイス テーブルとして登録できません。 これがデータベース テーブルのと共に表示されます、データベース テーブルが、インターフェイス テーブルとして登録されていない場合、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。 これらのテーブルが Oracle E-business アプリケーションに関連付けられているため、これらのテーブルの操作をする必要がありますコンテキストを設定するアプリケーション。  
  
  これらの成果物のアプリケーションのコンテキストを設定するには、バインドのプロパティまたは以前に指定したメッセージ コンテキスト プロパティの適切な値を提供する必要があります。  
  
### <a name="setting-application-context-for-poll-executenonquery-executereader-executescalar-and-composite-operations"></a>ポーリング、ExecuteNonQuery、ExecuteReader、ExecuteScalar、および複合操作のアプリケーション コンテキストの設定  
 成果物とは別のこれらのアーティファクトに対して実行されるさまざまな操作、アプリケーションのコンテキストを設定することもできます。  
  
-   ポーリング操作のアプリケーション コンテキストを設定するには、ことができますのみプロパティを使用するバインドとして指定した前。 アプリケーションのコンテキストの設定のポーリング操作が実行されるアーティファクトの適用可能なバインドのプロパティの適切な値を指定する必要があります。 たとえば、インターフェイス テーブルで、ポーリング操作を実行する場合は、インターフェイス テーブルのバインドのプロパティの値を指定する必要があります。  
  
-   ExecuteNonQuery、ExecuteReader、executescalar 操作のため、アプリケーションのコンテキストを設定するには、必要があります適切なの値を指定のバインドのプロパティまたはメッセージとして以前に指定したコンテキストのプロパティ。 これらの操作には、アプリケーションのコンテキストを設定の必要があります適切なの値を指定のバインドのプロパティまたはメッセージ コンテキスト プロパティは、操作が実行されるアーティファクトの適用をします。  
  
-   複合操作のアプリケーションのコンテキストを設定するには、バインドのプロパティまたは以前に指定したメッセージ コンテキスト プロパティの適切な値を提供する必要があります。 複合操作の設定アプリケーションのコンテキストにする必要があります適切なの値を指定のバインドのプロパティまたはメッセージ コンテキスト プロパティは、個々 の操作に適用します。 たとえば、複合操作には、2 つの操作が含まれていますバインドのプロパティまたはインターフェイス テーブルと、バインドのメッセージのコンテキスト プロパティの値を指定する必要がありますし、1 つは、インターフェイス テーブル、データベースで、その他のテーブル。プロパティまたはデータベース テーブルのメッセージ コンテキストのプロパティ。  
  
    > [!IMPORTANT]
    >  これらすべての操作では、それが Oracle E-business Suite (インターフェイス テーブル、インターフェイス ビュー、同時実行プログラム、または要求のセット) 内のアイテムに、操作を実行する場合、アプリケーションのコンテキストを設定するのには必須です。 基になるデータベース内のアイテムに、操作を実行している場合、アプリケーションのコンテキストを設定するのには必須ではありません。 たとえば、インターフェイス テーブルで、ポーリング操作を実行している場合、テーブルに対して、ポーリング操作を実行すると場合、は、アプリケーション コンテキストを設定する必要はありませんが、アプリケーションのコンテキストを設定する必要は。  
  
## <a name="setting-the-language-for-performing-operations"></a>操作を実行するための言語の設定  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]の Oracle E-business Suite では、多言語サポート (MLS) 機能をサポートし、操作を実行中に言語を指定することができます。 アダプターを公開、**言語**のプロパティのバインド、 **MlsSettings**プロパティのバインドと**言語**メッセージ コンテキスト プロパティの言語を指定するには操作を実行します。  
  
 指定された値、**言語**メッセージ コンテキスト プロパティの値を上書きする、**言語**のプロパティのバインド、 **MlsSettings**プロパティをバインドします。 詳細については、 **MlsSettings**プロパティ、バインドを参照してください[については、BizTalk Adapter for Oracle E-business Suite バインド プロパティを読み取る](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)します。  
  
##  <a name="Binding"></a> さまざまなアーティファクトのアプリケーションのコンテキストを設定するためのプロパティのバインド  
 次の表は、さまざまなアーティファクトのアプリケーションのコンテキストを設定する適切な値を指定する必要がありますのバインドのプロパティについての情報を提供します。  
  
|成果物|OracleEBSOrganizationId|OracleUserName|OraclePassword|OracleEBSResponsibilityKey<br />または<br />OracleEBSResponsibilityName|ApplicationShortName|  
|---|---|---|---|---|---|  
|インターフェイス テーブルとインターフェイス ビュー|√*|√|√|√||  
|同時実行プログラム|√*|√|√|√||  
|要求セット|√*|√|√|√||  
|PL/SQL Api|√*|√|√|√|√|  
|プロシージャと関数|√*|√|√|√|√|  
|[テーブルとビュー]|√*|√|√|√|√|  
  
 **√\* = オプション**  
  
> [!IMPORTANT]
> - 既定値、 **OracleEBSOrganizationId** (省略可) プロパティのバインドが null です。 値を指定する場合、 **OracleEBSOrganizationId**プロパティ、バインド、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]アプリケーション コンテキストの設定中に、セッションの ORG_ID をこの値に設定します。  
>   -   指定された値、 **OracleEBSResponsibilityKey**プロパティのバインドに指定された値よりも優先されます、 **OracleEBSResponsibilityName**プロパティをバインドします。  
  
 各バインド プロパティの詳細については、[については、BizTalk Adapter for Oracle E-business Suite バインド プロパティを読み取る](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)を参照してください。  
  
## <a name="see-also"></a>参照  
 [どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)
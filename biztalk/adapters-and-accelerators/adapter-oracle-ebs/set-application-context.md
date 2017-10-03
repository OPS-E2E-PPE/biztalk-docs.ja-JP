---
title: "アプリケーション コンテキストの設定 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e9697155-70c0-4173-80d2-d02d103c397b
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88db982be92123a13084892bfc396cb1d89c46ac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="set-application-context"></a>アプリケーション コンテキストの設定
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]でそれらの操作を実行する前にアプリケーション コンテキストの設定が一部の Oracle E-business Suite アイテム (インターフェイス テーブル、インターフェイス ビュー、同時実行プログラム、および要求のセット) ために必須です。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]アプリケーション コンテキストを設定するまで、これらの成果物の操作を実行することはできません。 ただし、基になる Oracle データベースでの成果物をユーザーの責任ですか、アプリケーションのコンテキストを設定するかどうか。  
  
## <a name="what-is-application-context"></a>アプリケーションのコンテキストとは  
 アプリケーション コンテキストは、ユーザー設定と、アイテムに対するアクセス制御を実装する Oracle E-business Suite でアイテムに関連付けられている要素のセットです。 アプリケーション コンテキストは、次の要素で構成されます。  
  
-   **ユーザー名**: Oracle E-business Suite に接続できるユーザー。  
  
-   **責任**: 責任はユーザーがそれらのデータおよび組織における各自の役割に適した関数にアクセスできる Oracle E-business Suite でアクセス レベルです。 役割には、運用ユニット、書籍のセットおよび windows、関数、およびその他の責任の制限付きのリスト、特定のアプリケーションへのアクセスを許可できます。 ユーザーに役割を割り当てる、により許可/アクセスを制限できます Oracle E-business Suite でユーザーのです。  
  
-   **組織 ID**: Oracle E-business Suite は、複数の組織の設定をサポートします。 これらの異なる組織は、値で、組織の ID、Org_ID テーブルの列に、これらの組織に関する情報を格納する Oracle E-business Suite で一意に識別されます。 により、組織の責任を割り当てまたは組織を明示的に選択する、許可/アクセスを制限できますユーザーの組織にします。  
  
 役割の詳細については、複数の組織、および Oracle E-business Suite で組織 ID を検索して、 [Oracle ヘルプ センター](http://docs.oracle.com)です。  
  
## <a name="setting-application-context"></a>アプリケーション コンテキストの設定  
 として、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite の成果物の確立またはアダプターで初期化されていないために、Oracle E-business Suite、アプリケーションのコンテキストで基になるデータベースに接続します。 初期化またはでこれらの成果物のため、アプリケーションのコンテキストを設定することができます、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]次のいずれかを使用します。  
  
-   **バインドのプロパティ**:[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]アプリケーション コンテキストを設定するための次のバインド プロパティを公開: **OracleEBSOrganizationId**、 **OracleUserName**、 **OraclePassword**、 **OracleEBSResponsibilityKey**、 **OracleEBSResponsibilityName**、および**ApplicationShortName**です。 さまざまな成果物のためのアプリケーション コンテキストを設定するこれらすべてのバインド プロパティの値を指定する必要はありません。 成果物のアプリケーション コンテキストの設定に必要なバインドのプロパティについては、次を参照してください。[設定アプリケーション コンテキストのさまざまなアイテムのバインディング プロパティ](#Binding)このトピックで後述します。  
  
-   **メッセージ コンテキスト プロパティ**:[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]アプリケーション コンテキストを設定するための次のメッセージ コンテキスト プロパティを公開: **ApplicationShortName**、 **OrganizationID**、 **ResponsibilityKey**、および**ResponsibilityName**です。 ユーザー名とパスワードを指定するためには、バインドのプロパティを使用する必要があります。 メッセージ コンテキスト プロパティを使用してアプリケーションのコンテキストを設定する方法については、次を参照してください。[アプリケーション コンテキストを使用してメッセージのコンテキスト プロパティを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-application-context-using-message-context-properties-in-oracle-ebs.md)です。  
  
> [!IMPORTANT]
>  指定された値、 **OracleEBSResponsibilityKey**バインディング プロパティの値を上書き、 **OracleEBSResponsibilityName**プロパティをバインドします。 同様に、指定された値、 **ResponsibilityKey**メッセージ コンテキスト プロパティに指定された値を上書きする、 **ResponsibilityName**メッセージ コンテキスト プロパティです。  
  
### <a name="precedence-order-binding-properties-vs-message-context-properties"></a>優先順位 (メッセージ コンテキスト プロパティとバインドのプロパティ)  
 バインドのプロパティおよびメッセージ コンテキスト プロパティの両方を使用して、アプリケーションのコンテキストを設定した場合、メッセージ コンテキスト プロパティに指定された値が優先され、バインドのプロパティに指定された値を上書きします。 たとえば、およびその他のバインドのプロパティとしてのメッセージ コンテキスト プロパティとしてアプリケーションの短い名前を指定する場合、メッセージ コンテキスト プロパティからアプリケーションの短い名前の値のみを取得し、関連のバインドから取り出され、残りの部分が、プロパティ。  
  
 **アプリケーションの短い名前の優先順位**  
  
 アプリケーション コンテキストを設定中には、アプリケーションの短い名前は、次の優先順位 (最高ランク) で使用されます。  
  
-   指定されたアプリケーションの短い名前、 **ApplicationShortName**メッセージ コンテキスト プロパティです。  
  
-   (インターフェイス テーブル、インターフェイス ビュー、同時実行プログラム、および要求セットの場合のみ) の SOAP アクションで指定されたアプリケーション短い名前。  
  
-   指定されたアプリケーションの短い名前、 **ApplicationShortName**プロパティをバインドします。  
  
 ただし、インターフェイス テーブル、インターフェイス ビュー、同時実行プログラム、および要求のセットをこの優先順位がのみ適用、アプリケーションのコンテキストを設定中にします。 インターフェイス テーブル、ビューのインターフェイスを識別するには、同時実行プログラム、および要求設定すると、SOAP アクションで短い名前を使用するアプリケーション。  
  
 **キーの責任と責任名用の優先順位**  
  
 アプリケーション コンテキストを設定中に責任のキーと責任名は、次の優先順位 (最高ランク) で使用されます。  
  
-   指定された責任キー、 **ResponsibilityKey**メッセージ コンテキスト プロパティです。  
  
-   指定された役割の名前、 **ResponsibilityName**メッセージ コンテキスト プロパティです。  
  
-   指定された責任キー、 **OracleEBSResponsibilityKey**プロパティをバインドします。  
  
-   指定された役割の名前、 **OracleEBSResponsibilityName**プロパティをバインドします。  
  
> [!TIP]
>  **バインドのアプリケーション コンテキストを設定するプロパティをメッセージ コンテキスト プロパティを使用する理由** バインドのプロパティを使用して、アプリケーションのコンテキストを設定した場合、Wcf-custom 送信ポート用の Oracle E-business アダプターは、特定の組織の ID、責任、およびバインドのプロパティに対して指定されたアプリケーションに対してのみ使用できます。 反対に、メッセージ コンテキスト プロパティを使用する場合は、「汎用」Wcf-custom 送信ポートを構成して、メッセージ レベルで、アプリケーションのコンテキストを設定します。  
  
### <a name="setting-application-context-for-interface-tables-interface-views-concurrent-programs-and-request-sets-mandatory"></a>インターフェイス テーブル、インターフェイス ビュー、同時実行プログラム、および要求セット (必須) のアプリケーション コンテキストの設定  
 インターフェイス テーブル、インターフェイス ビュー、同時実行のプログラムで操作を実行する前に、アプリケーションのコンテキストを設定する必要があり、要求の設定[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。 これを行うには、バインドのプロパティまたは以前に指定したとしてメッセージ コンテキスト プロパティの適切な値を指定する必要があります。  
  
> [!IMPORTANT]
>  インターフェイス テーブルに対する操作を行うことはできません、インターフェイス ビュー、同時実行プログラム、および要求は適切な値を必要なバインドのプロパティまたはメッセージ コンテキスト プロパティを設定する場合を除きに設定します。  
  
### <a name="setting-application-context-for-plsql-apis-procedures-functions-tables-and-views"></a>PL/SQL Api、プロシージャ、関数、テーブル、およびビューのアプリケーション コンテキストの設定  
  
-   **PL/SQL Api**: [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle データベースに加え、Oracle E-business Suite アプリケーションに関連付けられている PL/SQL Api を公開します。 Oracle データベースに関連付けられている PL/SQL Api のアプリケーション コンテキストを設定する省略可能ですは必須では、Oracle E-business Suite アプリケーションに関連付けられている PL/SQL Api のアプリケーション コンテキストを設定します。  
  
-   **プロシージャおよび関数**: Oracle データベースでプロシージャおよび関数に対する操作を実行するアプリケーションのコンテキストを設定する必要はありません。  
  
-   **テーブルとビューの**: Oracle データベースでテーブルおよびビューの操作を実行するアプリケーションのコンテキストを設定する必要はありません。 ただし、カスタムの Oracle E-business Suite アプリケーションのユーザーは、インターフェイス テーブルとして基本データベースのテーブルは登録できません。 データベース テーブルが、インターフェイス テーブルとして登録されていない場合にデータベース テーブルと共に表示されます、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。 これらのテーブルが Oracle E-business アプリケーションに関連付けられているため、操作をこれらのテーブルに対して設定する必要が、アプリケーションのコンテキスト。  
  
 これらの成果物のため、アプリケーションのコンテキストを設定するには、バインドのプロパティまたは以前に指定したとしてメッセージ コンテキスト プロパティの適切な値を指定する必要があります。  
  
### <a name="setting-application-context-for-poll-executenonquery-executereader-executescalar-and-composite-operations"></a>ポーリング、ExecuteNonQuery、ExecuteReader、ExecuteScalar、および複合操作のアプリケーション コンテキストの設定  
 別に、アイテムの移動、さまざまな操作はこれらの成果物で実行されるアプリケーションのコンテキストを設定することもできます。  
  
-   ポーリング操作のアプリケーション コンテキストを設定するにのみ使用できますのバインドのプロパティとして指定された前。 アプリケーションのコンテキストの設定は、ポーリング操作が実行される成果物の該当するバインドのプロパティの適切な値を指定する必要があります。 たとえば、インターフェイスのテーブルに、ポーリング操作を実行する場合は、インターフェイス テーブルのバインドのプロパティの値を指定する必要があります。  
  
-   ExecuteNonQuery、ExecuteReader、および ExecuteScalar 操作のため、アプリケーションのコンテキストを設定するには、必要があります適切なの値を指定のバインドのプロパティまたはメッセージとして以前に指定したコンテキスト プロパティです。 これらの操作には、アプリケーションのコンテキストを設定のする必要があります適切な値のバインドのプロパティまたはメッセージのコンテキスト プロパティを提供は、操作が実行される成果物の該当します。  
  
-   複合操作のため、アプリケーションのコンテキストを設定するには、バインドのプロパティまたは以前に指定したとしてメッセージ コンテキスト プロパティの適切な値を指定する必要があります。 複合操作のためには、アプリケーションのコンテキストを設定のする必要があります適切な値のバインドのプロパティまたはメッセージのコンテキスト プロパティを提供、個々 の操作に適用されます。 たとえば、複合操作には、2 つの操作が含まれている場合: インターフェイス テーブルおよびデータベースにもう 1 つの表にし、バインドのプロパティまたはインターフェイス テーブルだけでなく、バインディングのメッセージのコンテキスト プロパティの値を指定する必要がありますデータベース テーブルのメッセージ コンテキスト プロパティまたはプロパティ。  
  
    > [!IMPORTANT]
    >  これらすべての操作に対しては必須では Oracle E-business Suite (インターフェイス テーブル、インターフェイス ビュー、同時実行プログラムまたは要求のセット) 内のアイテムに、操作を実行する場合、アプリケーションのコンテキストを設定します。 基になるデータベース内のアイテムに、操作を実行している場合、アプリケーションのコンテキストを設定する必要はありません。 たとえば、インターフェイスのテーブルに、ポーリング操作を実行する場合は必須では、アプリケーションのコンテキストを設定する必要はない場合は、テーブルに対してポーリング操作を実行すると、アプリケーションのコンテキストを設定します。  
  
## <a name="setting-the-language-for-performing-operations"></a>操作を実行する言語の設定  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite の多言語サポート (MLS) 機能をサポートし、操作を実行中に言語を指定することができます。 アダプターを公開、**言語**下にあるプロパティのバインド、 **MlsSettings**プロパティのバインドと**言語**メッセージの言語を指定するコンテキスト プロパティ操作を実行します。  
  
 指定された値、**言語**メッセージ コンテキスト プロパティの値を上書きする、**言語**下にあるプロパティのバインド、 **MlsSettings**バインディング プロパティ。 詳細については、 **MlsSettings**バインディング プロパティを参照してください[BizTalk Adapter for Oracle E-business Suite バインド プロパティ読む](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)です。  
  
##  <a name="Binding"></a>さまざまな成果物のためのアプリケーション コンテキストを設定するためのバインドのプロパティ  
 次の表では、さまざまな成果物のためのアプリケーション コンテキストを設定する適切な値を指定する必要がありますのバインドのプロパティについて説明します。  
  
|成果物|OracleEBSOrganizationId|OracleUserName|OraclePassword|OracleEBSResponsibilityKey<br />または<br />OracleEBSResponsibilityName|ApplicationShortName|  
|---|---|---|---|---|---|  
|インターフェイスのテーブルとのインターフェイス ビュー|√*|√|√|√||  
|同時実行プログラム|√*|√|√|√||  
|要求のセット|√*|√|√|√||  
|PL/SQL Api|√*|√|√|√|√|  
|プロシージャと関数|√*|√|√|√|√|  
|[テーブルとビュー]|√*|√|√|√|√|  
  
 **√\* = 省略可能**  
  
> [!IMPORTANT]
>  -   既定値、 **OracleEBSOrganizationId** (省略可) プロパティのバインドが null です。 値を指定する場合、 **OracleEBSOrganizationId**バインディング プロパティを[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]アプリケーション コンテキストを設定中に、セッションの ORG_ID をこの値に設定します。  
> -   指定された値、 **OracleEBSResponsibilityKey**に指定された値をオーバーライドするプロパティのバインド、 **OracleEBSResponsibilityName**プロパティをバインドします。  
  
 これらの各バインド プロパティの詳細については、次を参照してください。 [BizTalk Adapter for Oracle E-business Suite バインド プロパティ読む](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)です。  
  
## <a name="see-also"></a>参照  
 [どのような操作をアダプターであるを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)
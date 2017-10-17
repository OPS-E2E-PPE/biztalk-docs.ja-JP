---
title: "ビジネス コンポーネント操作のメッセージ スキーマ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- message actions, for business component operations
- message schemas, for business component operations
ms.assetid: 753fdaa6-992f-4932-98ed-b7f2d66af7a9
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6d9f367502769923a8018f7bc777a9b79c70875
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="message-schemas-for-business-component-operations"></a>ビジネス コンポーネント操作のメッセージ スキーマ
## <a name="message-schemas-for-siebel-business-component-operations"></a>Siebel ビジネス コンポーネント操作のメッセージ スキーマ  
 次の表に、によって公開される操作のメッセージ スキーマを[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]Siebel ビジネス コンポーネントです。  
  
|操作|XML データ構造|Description|  
|---------------|-------------------|-----------------|  
|Insert|メッセージを挿入します。<br /><br /> `<Insert xmlns="[VERSION]/BusinessObjects/[BO]/[BC]/Operation">   <ArrayOf[BC]InsertRecord>     <[BC]InsertRecord>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </[BC]InsertRecord>     …   </ArrayOf[BC]InsertRecord> </Insert>`<br /><br /> [バージョン]、メッセージのバージョン文字列を =たとえば、"http://Microsoft.LobServices.Siebel/2007/03"です。<br /><br /> [BO]、ビジネス オブジェクトの名前を =たとえば、アカウントです。<br /><br /> [ビジネス継続性]、ビジネス コンポーネントの名前を =たとえば、アカウントです。<br /><br /> [FIELD1_NAME] = ビジネス コンポーネントのフィールド名です。たとえば、Account_x0020_Status です。<br /><br /> 応答メッセージを挿入します。<br /><br /> `<InsertResponset xmlns="[VERSION]/BusinessObjects/[BO]/[BC]/Operation">   <InsertResult>      <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">[ID1]</string>      <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">[ID2]</string>      …   </InsertResult> </InsertResponse>`<br /><br /> [バージョン]、メッセージのバージョン文字列を =たとえば、"http://Microsoft.LobServices.Siebel/2007/03"<br /><br /> [BO]、ビジネス オブジェクトの名前を =たとえば、アカウントです。<br /><br /> [ビジネス継続性]、ビジネス コンポーネントの名前を =たとえば、アカウントです。<br /><br /> [ID] = レコード ID です。たとえば、42-6ODBL です。|ビジネス コンポーネントを 1 つまたは複数のレコードを挿入します。<br /><br /> 応答には、レコード挿入されたすべてのレコードの Id にはが含まれています。<br /><br /> 少なくとも 1 つの挿入が成功した場合は、例外はスローされませんし、応答には、正常に挿入されたレコードの Id にが含まれます。 ただし、すべての挿入が失敗した場合、例外がスローされます (XmlReaderParsingException または TargetSystemException)。|  
|Query|クエリのメッセージ:<br /><br /> `<Query xmlns="[VERSION]/BusinessObjects/[BO]/[BC]/Operation">   <ViewMode>[View_mode]</ViewMode>   <[BC]QueryInputRecord>     <SearchExpr>[Search_expr]</SearchExpr>     <SortSpec>Sort_spec</SortSpec>     <QueryFields>       <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">[Field1_name]</string>       <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">[Field2_name]</string>       …     </QueryFields>   </[BC]QueryInputRecord> </Query>`<br /><br /> [バージョン]、メッセージのバージョン文字列を =たとえば、"http://Microsoft.LobServices.Siebel/2007/03"です。<br /><br /> [View_mode] を適用する表示モードを = です。 これは省略可能なパラメーターです。 使用可能な値については、Siebel のドキュメントを参照してください。<br /><br /> [Search_expr] = Siebel 検索式です。たとえば、[Name]「3 com *」のようにします。<br /><br /> [Sort_spec] = Siebel 並べ替え仕様です。たとえば、名前 (DESC) の場所です。<br /><br /> [FIELD1_NAME] = ビジネス コンポーネントのフィールド名です。たとえば、アカウントの状態。<br /><br /> クエリの応答メッセージ:<br /><br /> `<QueryResponse xmlns=" [VERSION]/BusinessObjects/[BO]/[BC]/Operation">   <QueryResult>     <[BC]QueryRecord>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </[BC]QueryRecord >   </QueryResult> </QueryResponse>`<br /><br /> [バージョン]、メッセージのバージョン文字列を =たとえば、"http://Microsoft.LobServices.Siebel/2007/03"です。<br /><br /> [BO]、ビジネス オブジェクトの名前を =たとえば、アカウントです。<br /><br /> [ビジネス継続性]、ビジネス コンポーネントの名前を =たとえば、アカウントです。<br /><br /> [FIELD1_NAME] = ビジネス コンポーネントのフィールド名です。たとえば、Account_x0020_Status です。|対象となるビジネス コンポーネントの 1 つまたは複数のレコードを照会します。 クエリ操作では、次のパラメーターを受け取ります。<br /><br /> \<SearchExpr > ターゲット ビジネス コンポーネントの下のすべてのレコードは、検索式と比較され、一致するレコードが返されます。<br /><br /> \<SortSpec > 並べ替え仕様は、検索式に一致するレコードが返される順序を決定します。 このパラメーターはオプションです。<br /><br /> \<QueryFields > フィールド名の一覧で、クエリ操作によって取得する必要があるターゲット business component のフィールドを指定します。 各レコードでは、このリストのフィールドのみが返されます。 ビジネス コンポーネント、XML でエンコードされた名前ではなく; 内のフィールドの元の名前を使用して、各フィールドを指定する必要があります。たとえば、"First_x0032_Name"ではなく [ファースト ネーム] です。 このパラメーターはオプションです。 クエリのフィールドが指定されていない場合は、すべてのフィールドが返されます。|  
|Update|メッセージを更新します。<br /><br /> `<Update xmlns="[VERSION]/BusinessObjects/[BO]/[BC]/Operation">   <ViewMode>[View_mode]</ViewMode>   <ArrayOf[BC]UpdateRecord>     <[BC]UpdateRecord>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …       <Id>[Record_ID]</Id>     </[BC]UpdateRecord>     …   </ArrayOf[BC]UpdateRecord> </Update>`<br /><br /> [バージョン]、メッセージのバージョン文字列を =たとえば、"http://Microsoft.LobServices.Siebel/2007/03"です。<br /><br /> [BO]、ビジネス オブジェクトの名前を =たとえば、アカウントです。<br /><br /> [ビジネス継続性]、ビジネス コンポーネントの名前を =たとえば、アカウントです。<br /><br /> [View_mode] を更新する必要があるレコードのクエリを実行するときに適用する表示モードを = です。 これは省略可能なパラメーターです。 使用可能な値については、Siebel のドキュメントを参照してください。<br /><br /> [FIELD1_NAME] = ビジネス コンポーネントのフィールド名です。たとえば、Account_x0020_Status です。<br /><br /> [Record_ID]; 更新するレコードのレコード ID を =たとえば、42-60DBL です。<br /><br /> 応答メッセージを更新します。<br /><br /> `<UpdateResponse xmlns="[VERSION]/BusinessObjects/[BO]/[BC]/Operation">   <UpdateResult>     <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">[ID1]</string>     <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">[ID2]</string>     …   </UpdateResult> </UpdateResponse>`<br /><br /> [バージョン]、メッセージのバージョン文字列を =たとえば、"http://Microsoft.LobServices.Siebel/2007/03"です。<br /><br /> [BO]、ビジネス オブジェクトの名前を =たとえば、アカウントです。<br /><br /> [ビジネス継続性]、ビジネス コンポーネントの名前を =たとえば、アカウントです。<br /><br /> [ID] = レコード ID です。たとえば、42-6ODBL です。|レコードの更新の一覧で指定された 1 つまたは複数のレコードを更新します。<br /><br /> 各レコード更新にはには、更新するフィールドの一覧と 1 つの必須が含まれています。 \<Id > 要素を更新するレコードを識別します。<br /><br /> 応答には、レコードのすべての更新されたレコードの Id の一覧が含まれています。<br /><br /> 少なくとも 1 つの更新が成功した場合は、例外はスローされませんし、応答には、正常に更新されたレコードの Id にが含まれます。 ただし、すべての更新プログラムが失敗した場合、例外がスローされます (XmlReaderParsingException または TargetSystemException)。|  
|DELETE|メッセージを削除します。<br /><br /> `<Delete xmlns="[VERSION]/BusinessObjects/[BO]/[BC]/Operation">   <ViewMode>[View_mode]</ViewMode>   <Id>     <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">[ID1]</string>     <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">[ID2]</string>     …   </Id>   <SearchExpr>Search_expr</SearchExpr> </Delete>`<br /><br /> [バージョン]、メッセージのバージョン文字列を =たとえば、"http://Microsoft.LobServices.Siebel/2007/03"です。<br /><br /> [BO]、ビジネス オブジェクトの名前を =たとえば、アカウントです。<br /><br /> [ビジネス継続性]、ビジネス コンポーネントの名前を =たとえば、アカウントです。<br /><br /> [View_mode] を削除する必要があるレコードのクエリを実行するときに適用する表示モードを = です。 これは省略可能なパラメーターです。 使用可能な値については、Siebel のドキュメントを参照してください。<br /><br /> [ID] = レコード ID です。たとえば、42-6ODBL です。<br /><br /> Search_expr = Siebel 検索式です。たとえば、[Name]「3 com *」のようにします。<br /><br /> 応答メッセージを削除します。<br /><br /> `<DeleteResponse xmlns="[VERSION]/BusinessObjects/[BO]/[BC]/Operation">   <DeleteResult>     <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">[ID1]</string>     <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">[ID2]</string>     …   </DeleteResult> </DeleteResponse>`<br /><br /> [バージョン]、メッセージのバージョン文字列を =たとえば、"http://Microsoft.LobServices.Siebel/2007/03"です。<br /><br /> [BO]、ビジネス オブジェクトの名前を =たとえば、アカウントです。<br /><br /> [ビジネス継続性]、ビジネス コンポーネントの名前を =たとえば、アカウントです。<br /><br /> [ID] = レコード ID です。たとえば、42-6ODBL です。|レコード Id のセットまたは検索式に一致する 1 つまたは複数のレコードを削除します。<br /><br /> **重要:**削除操作では、検索式または一連のレコード Id のいずれか。 同じ Delete 操作では、両方のパラメーターを指定できません。<br /><br /> 応答には、レコードの削除された行のすべての Id の一覧が含まれています。<br /><br /> 少なくとも 1 つの削除が成功した場合は、例外はスローされませんし、応答には、正常に削除されたレコードの Id にが含まれます。 ただし、すべての削除が失敗した場合、例外がスローされます (XmlReaderParsingException または TargetSystemException)。|  
|関連付け|メッセージに関連付けます。<br /><br /> `<Associate xmlns="[VERSION]/BusinessObjects/[BO]/[BC]/Operation">   <ViewMode>[View_mode]</ViewMode>   <ParentSearchExpr>Par_search</ParentSearchExpr>   <ParentMVGField>Field_name</ParentMVGField>   <ChildSearchExpr>Chld_search</ChildSearchExpr> </Associate>`<br /><br /> [バージョン]、メッセージのバージョン文字列を =たとえば、"http://Microsoft.LobServices.Siebel/2007/03"です。<br /><br /> [BO]、ビジネス オブジェクトの名前を =たとえば、アカウントです。<br /><br /> [ビジネス継続性]、ビジネス コンポーネントの名前を =たとえば、アカウントです。<br /><br /> [View_mode] 親呼び子ビジネス コンポーネントのレコードのクエリに適用する表示モードを = です。 値が指定されている場合、その値は親検索と子検索の両方に適用されます。 これは省略可能な引数です。 使用可能な値の詳細については、Siebel のドキュメントを参照してください。<br /><br /> [Par_search] 正確に 1 つの親ビジネス コンポーネントのレコードです一致する検索式を =。たとえば、[Id] のような AB-12345 です。<br /><br /> [Chld_search] 親ビジネス コンポーネント レコード; に関連付けられる 1 つの子ビジネス コンポーネントのレコードに一致する検索式を =たとえば、[Id] と同様に CD-12345 です。<br /><br /> [<] = 複数値グループ フィールド、親ビジネス コンポーネントの名前です。たとえば、' 課金内容に First Name' アカウント ビジネス コンポーネントです。<br /><br /> 応答メッセージを関連付けます。<br /><br /> `<AssociateResponse xmlns="[VERSION]/BusinessObjects/[BO]/[BC]/Operation">   <AssociateResult>     <ChildID>[CHILD_ID]</ChildID>     <ParentID>[PARENT_ID]</ParentID>   </AssociateResult> </AssociateResponse>`<br /><br /> [バージョン]、メッセージのバージョン文字列を =たとえば、"http://Microsoft.LobServices.Siebel/2007/03"です。<br /><br /> [BO]、ビジネス オブジェクトの名前を =たとえば、アカウントです。<br /><br /> [ビジネス継続性]、ビジネス コンポーネントの名前を =たとえば、アカウントです。<br /><br /> [CHILD_ID] = 子レコードの ID です。たとえば、42-6ODBL です。<br /><br /> [PARENT_ID] = 親レコードの ID です。たとえば、42-6ODBL です。|関連付け操作は、複数値のグループ (MVG) フィールドでビジネス コンポーネントに対してのみ確認できます。 親の検索式を指定することによってレコードと子レコードを関連付けます。<br /><br /> 関連付け操作:<br /><br /> -選択された子ビジネス コンポーネントの 1 つのレコードを選択した親ビジネス コンポーネント レコードを関連付けます<br /><br /> -1:1 の関連付けを確立します。 1 つの親レコードは 1 つの子レコードに関連付けられます<br /><br /> -1: n アソシエーションに加える必要のある 1:1 に対する複数の関連付けと M:N アソシエーションに加える必要のある複数のアソシエーションの 1: n<br /><br /> 注意してください。<br /><br /> 親検索式は、親テーブルに一意なレコードと一致する必要があります。<br /><br /> 子検索式は、子テーブルに一意なレコードと一致する必要があります。<br /><br /> 戻り値には、関連付けられている子の行のレコード ID と関連付けられている親の行のレコード ID が含まれています。 親検索式または子検索式に一致する 2 つ以上のレコードが返される場合、例外がスローされます。|  
|との関連付けを解除します。|メッセージの関連付けを解除します。<br /><br /> `<Dissociate xmlns="[VERSION]/BusinessObjects/[BO]/[BC]/Operation">   <ViewMode>[View_mode]</ViewMode>   <ParentSearchExpr>Par_search</ParentSearchExpr>   <ParentMVGField>Field_name</ParentMVGField>   <ChildSearchExpr>Chld_search</ChildSearchExpr> </Dissociate>`<br /><br /> [バージョン]、メッセージのバージョン文字列を =たとえば、"http://Microsoft.LobServices.Siebel/2007/03"です。<br /><br /> [BO]、ビジネス オブジェクトの名前を =たとえば、アカウントです。<br /><br /> [ビジネス継続性]、ビジネス コンポーネントの名前を =たとえば、アカウントです。<br /><br /> [View_mode] 親呼び子ビジネス コンポーネントのレコードのクエリに適用する表示モードを = です。 値が指定されている場合、その値は親検索と子検索の両方に適用されます。 これは省略可能な引数です。 指定できる値の詳細については、Siebel のドキュメントを参照してください。<br /><br /> [Par_search] 正確に 1 つの親ビジネス コンポーネントのレコードです一致する検索式を =。たとえば、[Id] のような AB-12345 です。<br /><br /> [Chld_search] = 検索式のレコードに一致する正確に 1 つの子ビジネス コンポーネントは、関連付けを解除する親ビジネス コンポーネントのレコードです。たとえば、[Id] と同様に CD-12345 です。<br /><br /> [<]、親ビジネス コンポーネントの複数値グループ fieldname を =たとえば、' 課金内容に First Name' アカウント ビジネス コンポーネントです。<br /><br /> 応答メッセージの関連付けを解除します。<br /><br /> `<DissociateResponse xmlns="[VERSION]/BusinessObjects/[BO]/[BC]/Operation">   <DissociateResult>     <ChildID>[CHILD_ID]</ChildID>     <ParentID>[PARENT_ID]</ParentID>   </DissociateResult> </DisocciateResponse>`<br /><br /> [バージョン]、メッセージのバージョン文字列を =たとえば、"http://Microsoft.LobServices.Siebel/2007/03"です。<br /><br /> [BO]、ビジネス オブジェクトの名前を =たとえば、アカウントです。<br /><br /> [ビジネス継続性]、ビジネス コンポーネントの名前を =たとえば、アカウントです。<br /><br /> [CHILD_ID] = 子レコードの ID です。たとえば、42-6ODBL です。<br /><br /> [PARENT_ID] = 親レコードの ID です。たとえば、42-6ODBL です。|関連付けを解除操作は、複数値のグループ (MVG) フィールドでビジネス コンポーネントに対してのみ確認できます。 親の検索式を指定することによってレコードと子レコードの関連付けを解除します。<br /><br /> 関連付けを解除操作:<br /><br /> 選択されている子ビジネス コンポーネントの 1 つのレコードを選択した親ビジネス コンポーネント レコードの関連付けを解除します。<br /><br /> 1:1 dissociation を確立します。 1 つの親レコードの 1 つの子レコードに関連付けが解除されます。<br /><br /> 1: n dissociation を加える必要のある複数の 1:1 dissociations と M:N dissociation を加える必要のある複数の 1: n dissociations<br /><br /> 検索の子の式が関連付けられているレコードと親検索式に一致する親レコード間で一意なレコードを一致する必要がありますに注意してください。<br /><br /> **重要:**は、子検索式に関連付けるおよび関連付けを解除操作の違いがあります。 関連付け操作では、検索の子の式は、child business component のすべてのレコードを検索します。 関連付けを解除の操作では、子検索式は、親レコードが親検索式に一致させる位置親ビジネス コンポーネント内のレコードに関連付けられている child business component のレコードだけを検索します。<br /><br /> 戻り値には、したがって子レコードのレコード ID と、したがって親レコードのレコード ID が含まれています。 親検索式または子検索式に一致する 2 つ以上のレコードが返される場合、例外がスローされます。|  
|Query_ [MVG_Child_Business_Comp]|Query_ [MVG_Child_Business_Comp] メッセージ:<br /><br /> `<Query_[CHILD_BC] xmlns="BusinessObjects/[BO]/[BC]/Operation">   <ViewMode>View_mode</ViewMode>   <ParentSearchExpr>Par_search</ParentSearchExpr>   <ParentMVGField>Field_name</ParentMVGField>   <[CHILD_BC]QueryInputRecord>     <SearchExpr>Chld_search </SearchExpr>     <QueryFields>       <string>field1</string>       <string>field2</string>       …     </QueryFields>   </[CHILD_BC]QueryInputRecord> </Query_[CHILD_BC]>`<br /><br /> [バージョン]、メッセージのバージョン文字列を =たとえば、"http://Microsoft.LobServices.Siebel/2007/03"です。<br /><br /> [BO]、ビジネス オブジェクトの名前を =たとえば、アカウントです。<br /><br /> [ビジネス継続性]、ビジネス コンポーネントの名前を =たとえば、アカウントです。<br /><br /> [View_mode]; を適用する表示モードを =0 ~ 9 を指定できます。 これは省略可能なパラメーターです。 これらの使用可能な値の詳細について、Siebel のドキュメントを参照してください。<br /><br /> [CHILD_BC] MVG parent business component のフィールドに関連付けられている子ビジネス コンポーネントの名前を =たとえば、(用アカウント親ビジネス コンポーネント) に問い合わせてください。<br /><br /> [Par_search]; 1 つの親ビジネス コンポーネント レコードと一致する検索式を =たとえば、[Id] のような AB-12345 です。<br /><br /> [<]、親ビジネス コンポーネントの複数値グループ fieldname を =たとえば、' 課金内容に First Name' アカウント business component ' です。<br /><br /> [Chld_search] 1 つ以上の子ビジネス コンポーネント レコード; と一致する検索式を =たとえば、[Id] と同様に CD-12345 です。<br /><br /> [field1]、[field2]、およびに = child business component のフィールドをクエリします。 操作によって取得する必要がある child business component のフィールドを指定するフィールド名の一覧です。 各レコードでは、このリストのフィールドのみが返されます。 でエンコードされた XML 名ではなく、child business component のフィールドの元の名前を使用して、各フィールドを指定する必要がありますたとえば、"First_x0032_Name"ではなく [ファースト ネーム] です。 このパラメーターはオプションです。<br /><br /> Query_ [MVG_Child_Business_Comp] 応答メッセージ:<br /><br /> `<Query_[CHILD_BC]Response xmlns="[VERSION]/BusinessObjects/[BO]/[BC]/Operation">   <Query_[CHILD_BC]Result>     <[CHILD_BC]QueryRecord>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </[CHILD_BC]QueryRecord >   </QueryResult> </QueryResponse>`<br /><br /> [バージョン]、メッセージのバージョン文字列を =たとえば、"http://Microsoft.LobServices.Siebel/2007/03"です。<br /><br /> [BO]、ビジネス オブジェクトの名前を =たとえば、アカウントです。<br /><br /> [ビジネス継続性]、ビジネス コンポーネントの名前を =たとえば、アカウントです。<br /><br /> [FIELD1_NAME] = ビジネス コンポーネントのフィールド名です。たとえば、Account_x0020_Status です。<br /><br /> [CHILD_BC] MVG parent business component のフィールドに関連付けられている子ビジネス コンポーネントの名前を =たとえば、(用アカウント親ビジネス コンポーネント) に問い合わせてください。|この操作は、MVG フィールドのビジネス コンポーネントの公開されます。<br /><br /> Parent business component の MVG フィールドに関連付けられている親レコードに関連付けられている子レコードを照会します。|  
  
## <a name="message-actions-for-siebel-business-component-operations"></a>Siebel ビジネス コンポーネント操作のメッセージの動作  
 次の表は、Siebel ビジネス コンポーネント操作の各 SOAP アクションを示します。 要求メッセージのアクションに表示される、アクション応答メッセージは追加された形式のみ"/応答"に要求メッセージのアクションです。たとえば、"http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert/response"です。  
  
|操作|操作|例|  
|---------------|------------|-------------|  
|Insert|[バージョン]/BusinessObjects/[BO]/[BC]/挿入|http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert|  
|Query|[バージョン]/BusinessObjects/[BO]/[BC]/[クエリ]|http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Query|  
|Update|[バージョン]/BusinessObjects/[BO]/[BC]/[更新]|http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Update|  
|DELETE|[バージョン]/BusinessObjects/[BO]/[BC] を削除します|http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Delete|  
|関連付け|[バージョン]/BusinessObjects/[BO]/[BC]/[関連付ける]|http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Associate|  
|との関連付けを解除します。|[バージョン]/BusinessObjects/[BO]/[BC]/[との関連付けを解除]|http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Dissociate|  
|Query_ [CHILD_BC]|[バージョン]/BusinessObjects/[BO]/[BC]/Query_ [CHILD_BC]|http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Query_Contact|  
  
 [バージョン]、メッセージのバージョン文字列を =たとえば、"http://Microsoft.LobServices.Siebel/2007/03"です。  
  
 [BO] = ビジネス オブジェクトの名前です。たとえば、アカウントです。  
  
 [BC] = ビジネス コンポーネントの名前です。たとえば、アカウントです。  
  
 親ビジネス コンポーネントの MVG フィールド; に関連付けられた子ビジネス コンポーネントの名前たとえば、(用アカウント親ビジネス コンポーネント) に問い合わせてください。  
  
 使用するときに、メッセージのアクションを明示的に指定する必要があります、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] 、BizTalk Server ソリューションでまたはを使用して、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]チャネル モデル。 詳細については、次を参照してください。 [Siebel アプリケーションの開発](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)です。  
  
## <a name="siebel-business-component-wcf-client-methods"></a>Siebel ビジネス コンポーネントの WCF クライアント メソッド  
 次の表に、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービスによって生成されるモデルのメソッドのシグネチャ、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]の Siebel ビジネス コンポーネントです。  
  
|操作|WCF サービス モデル メソッド|  
|---------------|------------------------------|  
|Insert|`string[] client.Insert([BC]InsertRecord[] ArrayOf[BC]InsertRecord);`<br /><br /> [BC] ビジネス コンポーネントの名前を =たとえば、アカウントです。|  
|Query|`[BC]QueryRecord[] client.Query(System.Nullable<short> ViewMode, [BC]QueryInputRecord [BC]QueryInputRecord);`<br /><br /> [BC] ビジネス コンポーネント、たとえば、アカウントの名前を = です。|  
|Update|`string[] client.Update(System.Nullable<short> ViewMode, [BC]UpdateRecord[] ArrayOf[BC]UpdateRecord);`<br /><br /> [BC] ビジネス コンポーネントの名前を =たとえば、アカウントです。|  
|DELETE|`string[] client.Delete(System.Nullable<short> ViewMode, string[] Id, string SearchExpr);`|  
|関連付け|`ParentChildRecord client.Associate(System.Nullable<short> ViewMode, string ParentSearchExpr, string ParentMVGField, string ChildSearchExpr);`|  
|との関連付けを解除します。|`ParentChildRecord client.Dissociate(System.Nullable<short> ViewMode, string ParentSearchExpr, string ParentMVGField, string ChildSearchExpr);`|  
|Query_ [MVG 子ビジネス コンポーネント]|`[CHILD_BC]QueryRecord[] client.Query_[CHILD_BC](../../core/system.md ViewModeshort ViewMode, string ParentSearchExpr, string ParentMVGField, [CHILD_BC]QueryInputRecord [CHILD_BC]QueryInputRecord);`<br /><br /> [CHILD_BC] MVG parent business component のフィールドに関連付けられている子ビジネス コンポーネントの名前を =たとえば、(用アカウント親ビジネス コンポーネント) に問い合わせてください。|  
  
## <a name="see-also"></a>参照  
 [メッセージと BizTalk Adapter for Siebel eBusiness Applications のメッセージ スキーマ](../../adapters-and-accelerators/adapter-siebel/messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)
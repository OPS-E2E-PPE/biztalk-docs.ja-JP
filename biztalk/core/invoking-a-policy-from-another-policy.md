---
title: 別のポリシーからポリシーを呼び出す |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b5bf658a-02a1-426a-abe5-8c9de673cf0d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 39f1366ccbf199db02bc60c0caf9015aba0cfc03
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994035"
---
# <a name="invoking-a-policy-from-another-policy"></a>別のポリシーからのポリシーの呼び出し
次のいずれかのメソッドを使用すると、ポリシー (子) を別のポリシー (親) から呼び出すことができます。  
  
- 呼び出す、 **Policy.Execute**親ポリシーから直接メソッド  
  
- ラップするヘルパー .NET コンポーネントのメソッドを呼び出し、 **Policy.Execute**親ポリシーからのメソッド  
  
  2 番目のメソッドを使用する利点は、処理前および処理後のコードを追加することができます、 **Policy.Execute**メソッド。 たとえば、子ポリシーで必要とされる任意のファクトを、このラッパー メソッドに作成できます。 以下のセクションでは、それぞれのメソッドの例を示します。  
  
## <a name="invoking-the-policyexecute-method-directly-from-the-parent-policy"></a>親ポリシーからの Policy.Execute メソッドの直接呼び出し  
 ここでは、大まかな手順を使用して、親ポリシーから、子ポリシーを呼び出す、 **Policy.Execute**メソッドを直接します。  
  
### <a name="adding-the-policyexecute-action-to-the-parent-policy"></a>親ポリシーへの Policy.Execute アクションの追加  
 次の手順が追加する手順、 **Policy.Execute**として XML ドキュメントをファクトとして子ポリシーに渡します親ポリシーにアクション メソッド。  
  
##### <a name="to-add-the-policyexecute-method-as-an-action-to-a-policy"></a>Policy.Execute メソッドをアクションとして親ポリシーに追加するには  
  
1.  [ファクト エクスプ ローラー] ウィンドウ、 **.NET クラス**タブ。  
  
2.  右クリック **.NET アセンブリ**、 をクリックし、**参照**します。  
  
3.  選択**Microsoft.RuleEngine**から、 **.NET アセンブリ**ボックスの一覧をクリックして**OK**します。  
  
4.  展開**ポリシー**します。  
  
5.  ドラッグ**Execute (Object facts)** または**Execute (Object facts, IRuleSetTrackingInterceptor trackingInterceptor)** [THEN] ペインにします。  
  
6.  をクリックして、 **XML スキーマ**ノード。  
  
    > [!NOTE]
    >  このサンプル シナリオでは、ファクトとして親ポリシーに送信される XML ドキュメントが、ファクトとして子ポリシーに渡されます。 代わりに、子ポリシー用のファクトを作成する .NET メソッドを呼び出すこともできます。  
  
7.  右クリック**スキーマ**、 をクリックし、**参照**します。  
  
8.  クリックして、ファクトとして渡す XML ドキュメントのスキーマを選択**オープン**します。  
  
9. ドラッグ*\<スキーマ名\>* の最初の引数は、.xsd、 **Policy.Execute**子ポリシーのファクトとして親ポリシーに渡される XML ドキュメントを渡す方法です。  
  
10. 使用する場合、 **Execute**を受け取らないメソッド、 **IRuleSetTrackingInterceptor** 2 番目の引数として、次の手順をスキップします。  
  
11. をクリックして、 **.NET クラス**タブ。  
  
12. ドラッグ**DebugTrackingInterceptor**で**Microsoft.RuleEngine**の 2 番目の引数、 **Policy.Execute**メソッド。  
  
    > [!NOTE]
    >  この操作を実行する場合、クライアントがのインスタンスを渡す必要があります、 **DebugTrackingInterceptor**クラスをインスタンスをファクトとして子ポリシーに渡します親ポリシーのファクトとして。 コンス トラクターをドラッグする代わりに、 **DebugTrackingInterceptor**クラスのインスタンスが自動的に作成するようにします。  
  
### <a name="modifying-the-client-application-that-invokes-the-parent-policy"></a>親ポリシーを呼び出すクライアント アプリケーションの変更  
 親ポリシーを呼び出すクライアントのインスタンスを作成、**ポリシー**クラスをパラメーターとして子ポリシーの名前をファクトとして他のファクトと共に親ポリシーに渡します。 このアクションを説明するサンプル コードを次に示します。  
  
```  
DebugTrackingInterceptor dti = new DebugTrackingInterceptor("PolicyTracking.txt");  
Policy policy = new Policy("ParentPolicy");  
object[] facts = new object[3];  
facts[0] = txd;  
facts[1] = new Policy("ChildPolicy");  
facts[2] = new DebugTrackingInterceptor("PolicyTracking2.txt");  
policy.Execute(facts, dti);  
policy.Dispose();  
```  
  
 クライアントが BizTalk オーケストレーションの場合は、内のファクトを作成するコードを配置する必要があります、**式**図形し、ファクトをパラメーターとして渡して、**ルールの呼び出し**図形。  
  
## <a name="invoking-a-net-wrapper-method-from-the-parent-policy"></a>親ポリシーからの .NET ラッパー メソッドの呼び出し  
 ここへの呼び出しをラップする .NET メソッドを呼び出すための大まかな手順、 **Policy.Execute**親ポリシーからのメソッド。  
  
### <a name="creating-the-utility-net-class"></a>ユーティリティ .NET クラスの作成  
  
##### <a name="to-create-the-utility-class"></a>ユーティリティ クラスを作成するには  
  
1.  .NET クラス ライブラリ プロジェクトを作成し、このプロジェクトにクラスを追加します。  
  
2.  呼び出す静的メソッドを追加、 **Policy.Execute**に次のサンプル コードに示すように、パラメーターとして渡される名前のポリシーを呼び出すメソッド。  
  
    ```  
    public static void Execute(string policyName, TypedXmlDocument txd)  
    {  
        DebugTrackingInterceptor dti = new   DebugTrackingInterceptor("PolicyTracking.txt");  
        Policy policy = new Policy("ParentPolicy");  
        object[] facts = new object[3];  
        facts[0] = txd;  
        facts[1] = new Policy("ChildPolicy");  
        facts[2] = new DebugTrackingInterceptor("PolicyTracking2.txt");  
        policy.Execute(facts, dti);  
        policy.Dispose();  
    }   
    ```  
  
3.  必ず、 **StaticSupport**レジストリ キーが 1 または 2 に設定します。 レジストリ キーの詳細については、次を参照してください。[クラスの静的メンバーを呼び出す](../core/invoking-static-members-of-a-class.md)します。  
  
    > [!NOTE]
    >  静的メソッドの代わりにインスタンス メソッドを使用することもできます。 インスタンス メソッドを使用する場合、クライアントは、ヘルパー .NET クラスのインスタンスをファクトとして親ポリシーに渡す必要があります。  
  
### <a name="modifying-the-client-application"></a>クライアント アプリケーションの変更  
 クライアントが親ポリシーを呼び出し、親ポリシーが、子ポリシーを呼び出すヘルパー メソッドを呼び出します。 クライアントのサンプル コードを次に示します。  
  
```  
facts[0] = txd;  
facts[1] = new PolicyExecutor(txd);  
//call the first or parent policy  
Policy policy = new Policy(policyName);  
DebugTrackingInterceptor dti = new DebugTrackingInterceptor("PolicyTracking.txt");  
policy.Execute(facts, dti);  
policy.Dispose();  
```  
  
> [!NOTE]
>  メソッドがインスタンス メソッドの場合、クライアントは、ヘルパー .NET クラスのインスタンスを作成し、ファクトとして親ポリシーに渡す必要があります。  
  
> [!NOTE]
>  クライアントが BizTalk オーケストレーションの場合は、内のファクトを作成するコードを配置する必要があります、**式**図形し、ファクトをパラメーターとして渡して、**ルールの呼び出し**図形。
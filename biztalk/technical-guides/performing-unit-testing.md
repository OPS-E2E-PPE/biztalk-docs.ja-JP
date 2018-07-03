---
title: 単体テストの実行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 40275d0b-b2ee-400c-9ef5-b9386ab0ae53
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36ede86266ea02b05249aa3edd655f3b10a27f3a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007587"
---
# <a name="performing-unit-testing"></a>単体テストの実行
単体テストでは、コンポーネント レベルでのフォーカスし、BizTalk ソリューションの個々 のコンポーネントがどおり動作するかどうかを検証する合格/不合格のテストでは基本的にします。 単体テスト、BizTalk ソリューションのいくつかのオプションがあります。  

## <a name="using-visual-studio"></a>Visual Studio の使用  
 単体テスト機能は、Visual Studio 2008 で使用可能な以降です。 Visual Studio で使用可能であるテスト機能の詳細については、次を参照してください。[アプリケーションのテスト](http://go.microsoft.com/fwlink/?LinkId=159595)(http://go.microsoft.com/fwlink/?LinkId=159595)します。  

 BizTalk Server には、スキーマ、マップ、およびパイプラインの単体テストを作成するユーザーを有効にする単体テスト機能も用意されています。 この機能の詳細については、次を参照してください。 [BizTalk Server プロジェクトでの Unit Testing](http://go.microsoft.com/fwlink/?LinkId=158270) (http://go.microsoft.com/fwlink/?LinkId=158270)します。  

> [!NOTE]  
>  Visual Studio は、単体テストのオーケストレーション、スキーマ、パイプライン、およびパイプライン コンポーネントなどの BizTalk アイテムに便利です。 BizTalk Server では、BizTalk アイテムをテストする Visual Studio Team System で使用できるテストのクラスを提供します。  

## <a name="using-non-microsoft-tools"></a>Microsoft 以外のツールを使用します。  
 BizTalk ソリューションのテスト単位の他の 2 つの一般的に使用されるツールは**BizUnit**と**NUnit**します。 **BizUnit** Visual Studio Team System Test Edition とシームレスに連携します。 同様に、 **NUnit**として実行できるように、テストを簡単に変更することができます-Visual Studio Team System Test Edition にします。 これらのツールの詳細については、次を参照してください。[テスト用ツール](~/technical-guides/tools-for-testing.md)します。  

> [!NOTE]  
>  使用**BizUnit**と**NUnit** Microsoft でサポートされていないと、Microsoft がこれらのプログラムの適合性に関する保証をいたしません。 これらのプログラムは、ユーザー自身の責任で使用してください。  

## <a name="using-the-biztalk-server-sdk"></a>BizTalk Server SDK の使用  
 単位を実行するテストで使用できるユーティリティを使用して個々 の BizTalk アイテムの[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]SDK。 次の表では、単体テストに使用できる SDK のユーティリティの概要を示します。  


|    **Utility**     |                                                                                                                                                                                                                                                                   **用途**                                                                                                                                                                                                                                                                   |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| AS2 送信者ユーティリティ |                                                                                                                                                                                              1 台のコンピューター上の Web サイトに AS2 メッセージを送信できます。 このユーティリティは、個別のコンピュータからの AS2 メッセージの送信をシミュレートします。                                                                                                                                                                                              |
|     DSDump.exe     |                                                                                  ドキュメント スキーマ構造をダンプするために使用します。この構造は、1 つ以上の XSD スキーマのメモリ内簡易表現で、フラット ファイルの注釈を含む場合と含まない場合があります。 $Root$0$3$2 などの解析エンジン エラーが発生し、デコードする必要がある場合に、このツールが役立ちます。 $ 後の数値は、ドキュメント スキーマに表示される、0 から始まるインデックスまたはレコードを意味します。                                                                                   |
|     FFAsm.exe      |                                                                                                                                                                        送信パイプラインをエミュレートすることにより、フラット ファイル アセンブラー コンポーネントを直接呼び出して実行し、ユーザーの XML ドキュメント (複数可) をフラット ファイル ドキュメントにシリアル化またはアセンブルするようすを表示します。                                                                                                                                                                        |
|     FFDasm.exe     |                                                                                                                                                                 受信パイプラインをエミュレートすることにより、フラット ファイル逆アセンブラー コンポーネントを直接呼び出して実行し、ユーザーのフラット ファイル ドキュメントを 1 つ以上の XML ドキュメントに解析または逆アセンブルするようすを表示します。                                                                                                                                                                  |
|    Pipeline.exe    | 実行を送信または受信パイプラインです。1 つまたは複数の入力ドキュメントと部分、XSD スキーマ、および関連情報を受け取る生成、パイプラインの後の出力ドキュメントを実行します。 Pipeline.exe はアクセスしない[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース、BizTalk Framework アセンブラーおよび逆アセンブラー コンポーネントでアクセスを含むためのパイプライン[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実行中にデータベースがサポートされていません。 |
|     XMLAsm.exe     |                                                                                                                                                                    送信パイプラインをエミュレートすることにより、XML アセンブラー コンポーネントを直接呼び出して実行し、ユーザーの XML ドキュメント (複数可) を 1 つの出力 XML ドキュメントにシリアル化、アセンブル、またはエンベロープするようすを表示します。                                                                                                                                                                    |
|    XMLDasm.exe     |                                                                                                                                                                受信パイプラインをエミュレートすることにより、XML 逆アセンブラー コンポーネントを直接呼び出して実行し、ユーザーの XML ドキュメントを 1 つ以上の XML ドキュメントに解析、逆アセンブル、またはエンベロープ解除するようすを表示します。                                                                                                                                                                |

 使用できるユーティリティの詳細については、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SDK を参照してください[SDK のユーティリティ](http://go.microsoft.com/fwlink/?LinkId=154387)(<http://go.microsoft.com/fwlink/?LinkId=154387>)。  

## <a name="see-also"></a>参照  
 [テスト用ツール](~/technical-guides/tools-for-testing.md)
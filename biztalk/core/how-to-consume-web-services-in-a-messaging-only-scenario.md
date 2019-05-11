---
title: メッセージングのみのシナリオのサービスの Web を使用する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 66873959-5b1b-4d9b-ad19-f083670420b8
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34a58ae2d7ece7de0814359779de0fef95294ed5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340144"
---
# <a name="how-to-consume-web-services-in-a-messaging-only-scenario"></a>メッセージングのみのシナリオで Web サービスを使用する方法
SOAP アダプターの新しい機能強化の 1 つは、コンテンツ ベースのルーティング送信ポートを使用して、メッセージングのみのシナリオで Web サービスを呼び出す機能です。 この機能により、オーケストレーションを作成せずに Web サービスを使用することが可能になります。 また、メッセージがオーケストレーションで処理されないため、Web サービスの使用におけるパフォーマンスが向上します。  
  
 メッセージングのみのシナリオで Web サービスを使用するには、次の手順を実行します。  
  
-   Web サービスを呼び出すためのプロキシ ライブラリおよび XML スキーマを作成します。  
  
-   Web サービスを使用するための送信ポートおよび受信場所を構成します。  
  
### <a name="to-create-a-proxy-library-and-xml-schemas-for-invoking-web-services"></a>Web サービスを呼び出すためのプロキシ ライブラリおよび XML スキーマを作成するには  
  
1. Web サービスの URL を決定します。  
  
2. 開く、**空の BizTalk Server プロジェクト**で、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ソリューション。 BizTalk Server プロジェクトを作成する方法の詳細については、次を参照してください。 [BizTalk プロジェクトを作成する方法](../core/how-to-create-biztalk-projects.md)します。  
  
   > [!NOTE]
   >  このチュートリアルでは、BizTalk Server プロジェクトを利用して、Web サービスで使用するプロキシ ライブラリおよび XML スキーマを作成します。 同じ目的で、.NET Framework 4.0 の SDK の Wsdl.exe および Xsd.exe を使用することができますも。  
  
3. ソリューション エクスプ ローラーで、BizTalk Server プロジェクトの名前を右クリックし をクリックし、**サービス参照の追加**します。  
  
4. **サービス参照の追加**ダイアログ ボックスで、をクリックして**詳細**します。  
  
5. **サービス参照設定** ダイアログ ボックスをクリックします**Web 参照の追加**で、**互換性**セクション。  
  
6. **Web 参照の追加** ダイアログ ボックスで、次の操作を行います。  
  
   1.  **URL**フィールドを Web サービスの URL を入力し、をクリックし、**移動**します。  
  
   2.  **Web 参照名**フィールドを名前空間の名前を入力し、をクリックし、**参照の追加**します。  
  
7. Web 参照は、下に表示されます**Web 参照**ソリューション エクスプ ローラーでノード。  
  
   > [!TIP]
   >  Web 参照を BizTalk プロジェクトに追加した後、 **Web 参照の追加**プロジェクト名を右クリックすると、コマンドは直接利用または**参照**または**のWeb参照**.  
  
8. ソリューション エクスプ ローラーでプロジェクト名を右クリックし をクリックし、**プロパティ**をプロジェクト デザイナーを起動します。  
  
9. プロジェクト デザイナーで、クリックして、**署名**タブ。  
  
10. 選択**アセンブリに署名**オプションで、ドロップダウン リストをクリックして、**厳密な名前キー ファイルを選択して**、順にクリックします**参照**します。  
  
11. 参照しアセンブリ キー ファイルを選択してクリックして**オープン**します。  
  
12. ソリューション エクスプ ローラーでプロジェクト名を右クリックし をクリックし、**ビルド**します。  
  
13. ソリューション エクスプ ローラーでプロジェクト名を右クリックし をクリックし、**デプロイ**します。  
  
### <a name="to-configure-a-send-port-and-receive-location-for-consuming-a-web-service"></a>Web サービスを使用するための送信ポートおよび受信場所を構成するには  
  
1.  BizTalk Server 管理コンソールで、送信ポートを作成します。 詳細については、次を参照してください。[送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)します。 送信ポートを作成するときは、トランスポートの種類またはトランスポート プロトコルとして SOAP を選択します。  
  
2.  次の設定を使用して、SOAP 送信ポートを構成します。 詳細については、次を参照してください。 [SOAP 送信ポートを構成する方法](../core/how-to-configure-a-soap-send-port.md)します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**次の設定**|次のプロパティを指定するために、このオプションを選択します。|  
    |**アセンブリ名**|前の手順で作成したアセンブリを選択します。 アセンブリの完全修飾名は、SOAP アダプターに書き込まれます**AssemblyName**プロパティ。|  
    |**型名**|呼び出す Web メソッドを含むクラスの名前を指定します。 型名は、SOAP アダプターに書き込まれます**TypeName**プロパティ。|  
    |**メソッド名**|リスト ボックスでメソッドの 1 つを指定します。 Web メソッドが、Soap アダプターに書き込まれる**MethodName**プロパティ。|  
  
    > [!NOTE]
    >  コンテンツ ベースのルーティング (CBR) を使用する場合は、送信ポートのフィルターを構成します。 詳細については、次を参照してください。[送信ポートのフィルターを構成する方法](../core/how-to-configure-filters-for-a-send-port.md)します。  
  
    > [!NOTE]
    >  呼び出された Web サービスからの応答メッセージに対するサブスクライバーがない場合は、ルーティング障害のエラーが発生します。  
  
## <a name="see-also"></a>参照  
 [Web サービスの利用](../core/consuming-web-services.md)
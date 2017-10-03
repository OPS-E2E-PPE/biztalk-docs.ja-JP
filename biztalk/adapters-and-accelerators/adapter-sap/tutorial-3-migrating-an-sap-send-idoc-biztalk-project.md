---
title: "チュートリアル 3: SAP を移行する BizTalk プロジェクトの IDOC を送信 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- migrating, SAP Send IDOC BizTalk project
- migration
ms.assetid: c0a11432-5388-4054-8996-08a957cc02eb
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52f8bc638d1adefe952ce055542706d11e0ca61f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-3-migrating-an-sap-send-idoc-biztalk-project"></a>チュートリアル 3: SAP 送信 IDOC の BizTalk プロジェクトを移行します。
Microsoft BizTalk Server に付属している SAP アダプターの以前のバージョンが WCF ベース異なる[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]など、多くの点で。  
  
-   デザイン時に、BizTalk プロジェクトを作成する操作。  
  
-   メタデータの取得エクスペリエンス。  
  
-   スキーマ ファイル名と名前空間。  
  
-   データは、マッピングを入力します。  
  
-   アダプターを使用して実行できる操作です。  
  
-   BizTalk Server 管理コンソールで物理ポートの構成。  
  
 これらの相違点が含まれるトピックで説明した[を移行する BizTalk プロジェクト作成を使用して、前のバージョンの SAP アダプター](http://msdn.microsoft.com/library/a486bac9-8952-43fd-8099-413f1491de37)です。  
  
 ただし、アダプターの以前のバージョンを使用して作成された BizTalk プロジェクトに変更を加えるし、WCF ベースで動作させるため[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
 このチュートリアルでは、アダプターの以前のバージョンを使用して作成された既存の BizTalk プロジェクトに加える必要があります変更について説明します。  
  
> [!NOTE]
>  ここでは簡略化のため、このチュートリアルでは、SAP アダプターの以前のバージョンを vPrev SAP アダプターと呼びます。 同様に、vPrev SAP アダプターを使用する BizTalk プロジェクトが参照されます vPrev BizTalk プロジェクトです。  
  
## <a name="sample-used-for-the-tutorial"></a>チュートリアルでは、使用されるサンプル  
 このチュートリアルは、IDOC を SAP システムに送信する vPrev BizTalk プロジェクトを移行する方法を示すサンプル (SendIDOC_Migration) に基づいています。 サンプルが付属して、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。 詳細については、次を参照してください。[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)です。  
  
## <a name="prerequisites"></a>前提条件  
  
-   VPrev BizTalk プロジェクトが必要です。 このチュートリアルには、SAP システムに BOMDOC IDOC を送信する BizTalk プロジェクトが含まれます。  
  
-   VPrev SAP アダプターを使用して SAP システムに送信するフラットファイル BOMDOC IDOC が必要です。 このチュートリアルで提供されたサンプルには、このフラット ファイル IDOC が含まれています。  
  
-   [厳密な名前キー ファイルを作成し、ツールの説明](../../adapters-and-accelerators/adapter-sap/prerequisites-to-create-sap-applications.md)
  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>アダプターの以前のバージョンを使用して作成された BizTalk プロジェクトを理解します。  
 IDOC を送信する vPrev BizTalk プロジェクトの主要な構成要素は次のとおりです。  
  
-   **BizTalk オーケストレーション**です。 これは、ファイルの場所からフラット ファイル IDOC を取得し、SAP を使用して SAP システムに IDOC の送信ポートを送信する簡単なオーケストレーションです。 BizTalk プロジェクトには、オーケストレーションで使用できるように、フラット ファイル IDOC を XML に変換する、フラット ファイル逆アセンブラーが含まれています。 XML IDOC を SAP に送信ポート vPrev で使用すると、前に、フラット ファイル アセンブラーを使用してフラット ファイル IDOC に変換されます。  
  
-   **SAP システムに送信する IDOC のスキーマ**です。 このチュートリアルでは、BOMDOC01 IDOC を SAP システムに送信する BizTalk プロジェクトを実行します。 IDOC に対して生成されたスキーマは、BOMDOC01.xsd です。 このスキーマは、vPrev SAP アダプターを使用して生成されます。  
  
-   **フラット ファイル IDOC**です。 これは、フラット ファイル IDOC を SAP システムに送信されます。  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>BizTalk プロジェクトを移行する方法は、アダプターの以前のバージョンを使用して作成されました。  
 この移行チュートリアルの目的は、vPrev SAP アダプターの送信ポートではなく Wcf-custom 送信ポートを使用して SAP システムにフラット ファイル IDOC を送信するためです。 どのような設定が必要、Wcf-custom 送信ポートの詳細については、前に、まず vPrev 送信 IDOC オーケストレーションに必要などのような物理ポートを理解する必要があります。  
  
-   ファイルは、フラット ファイル IDOC を取得するポートを受信します。 このポートは、フラット ファイルを vPrev SAP アダプターを使用して生成されたスキーマ (BOMDOC01.xsd) に準拠する XML に変換するのに BizTalk アプリケーションで使用可能なフラット ファイル逆アセンブラー パイプラインを使用します。  
  
-   VPrev SAP では、フラット ファイル IDOC を SAP システムに送信ポートを送信します。 フラット ファイルを送信する前に、ポートは、XML IDOC フラット ファイル IDOC に変換するのに、フラット ファイル アセンブラーを使用します。  
  
 既存の vPrev BizTalk プロジェクトを移行するには、ファイルを変更する必要はありません、フラット ファイル IDOC を取得し、フラット ファイル IDOC をフラット ファイル逆アセンブラーを使用して XML に変換される受信ポート。 右側の構成設定で新しい Wcf-custom 送信ポートを構成する必要があるだけです。 このチュートリアルは、WCF ベースを使用して SAP システムに Idoc を送信する Wcf-custom 送信ポートを構成する方法を示します[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [手順 1: 構築して、IDOC を送信するため vPrev BizTalk プロジェクトを配置](../../adapters-and-accelerators/adapter-sap/step-1-build-and-deploy-the-vprev-biztalk-project-for-sending-an-idoc.md)  
  
-   [手順 2: Wcf-custom 一方向送信ポートを構成します。](../../adapters-and-accelerators/adapter-sap/step-2-configure-a-wcf-custom-one-way-send-port.md)  
  
-   [手順 3: 移行後のアプリケーションをテストします。](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application2.md)  
  
## <a name="see-also"></a>参照  
 [SAP アダプタ チュートリアル](../../adapters-and-accelerators/adapter-sap/sap-adapter-tutorials.md)
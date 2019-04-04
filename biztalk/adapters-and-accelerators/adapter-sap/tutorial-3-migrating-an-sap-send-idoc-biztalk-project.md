---
title: 'チュートリアル 3: SAP を移行する IDOC の BizTalk プロジェクトの送信 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migrating, SAP Send IDOC BizTalk project
- migration
ms.assetid: c0a11432-5388-4054-8996-08a957cc02eb
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9aaf4fae9afaad2900f0354aec9f1eeb3f3de0ee
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966451"
---
# <a name="tutorial-3-migrating-an-sap-send-idoc-biztalk-project"></a>チュートリアル 3: を SAP IDOC 送信 BizTalk プロジェクトを移行します。
WCF ベースの Microsoft BizTalk Server に同梱されている SAP アダプターの以前のバージョンとは異なる[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]など、多くの点で。  
  
- BizTalk プロジェクトの作成、デザイン時エクスペリエンス。  
  
- メタデータの取得エクスペリエンス。  
  
- スキーマ ファイル名と名前空間。  
  
- データ型のマッピング。  
  
- アダプターを使用して実行できる操作。  
  
- BizTalk Server 管理コンソールで物理ポートの構成。  
  
  これらの相違点については、トピックで[を移行する BizTalk プロジェクト作成を使用して、前のバージョン、SAP アダプターの](http://msdn.microsoft.com/library/a486bac9-8952-43fd-8099-413f1491de37)します。  
  
  ただし、アダプターの以前のバージョンを使用して作成された BizTalk プロジェクトに変更を加えるし、WCF ベースと連携させるため[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
  このチュートリアルでは、アダプターの以前のバージョンを使用して作成された既存の BizTalk プロジェクトにする必要があります変更について説明します。  
  
> [!NOTE]
>  説明を簡潔にするため、このチュートリアルでは SAP アダプターの以前のバージョンを vPrev SAP アダプターとして指す場合は。 同様に、vPrev SAP アダプターを使用する BizTalk プロジェクトは vPrev BizTalk プロジェクトに参照されます。  
  
## <a name="sample-used-for-the-tutorial"></a>このチュートリアルで使用されるサンプル  
 このチュートリアルは、SAP システムに IDOC を送信する vPrev BizTalk プロジェクトを移行する方法を示すサンプル (SendIDOC_Migration) に基づいています。 サンプルが付属、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。 詳細については、[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)を参照してください。  
  
## <a name="prerequisites"></a>前提条件  
  
-   VPrev BizTalk プロジェクトが必要です。 このチュートリアルには、SAP システムに BOMDOC IDOC を送信する BizTalk プロジェクトが含まれます。  
  
-   VPrev SAP アダプターを使用して、SAP システムに送信するフラットファイル BOMDOC IDOC が必要です。 このチュートリアルでは提供されたサンプルには、このフラット ファイル IDOC が含まれています。  
  
-   [厳密な名前のキー ファイルの作成と、ツールの説明](../../adapters-and-accelerators/adapter-sap/prerequisites-to-create-sap-applications.md)
  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>アダプターの以前のバージョンを使用して作成された BizTalk プロジェクトを理解します。  
 IDOC を送信する vPrev BizTalk プロジェクトの主要な構成要素は次のとおりです。  
  
-   **BizTalk オーケストレーション**します。 これは、ファイルの場所からフラット ファイル IDOC を取得し、SAP を使用して SAP システムに IDOC の送信ポートを送信する簡単なオーケストレーションです。 BizTalk プロジェクトには、オーケストレーションで使用できるように、XML、フラット ファイル IDOC に変換するフラット ファイル逆アセンブラーが含まれています。 XML IDOC が SAP に送信ポート vPrev によって使用される、前に、フラット ファイル アセンブラーを使用してフラット ファイル IDOC に変換されます。  
  
-   **SAP システムに送信する IDOC のスキーマ**します。 このチュートリアルでは、BOMDOC01 IDOC を SAP システムに送信する BizTalk プロジェクトを実行します。 IDOC に対して生成されたスキーマは、BOMDOC01.xsd です。 VPrev SAP アダプターを使用して、このスキーマが生成されます。  
  
-   **フラット ファイル IDOC**します。 これは、フラット ファイル IDOC を SAP システムに送信されます。  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>BizTalk プロジェクトを移行する方法は、アダプターの以前のバージョンを使用して作成されました。  
 この移行のチュートリアルの目的は、vPrev SAP アダプターの送信ポートではなく Wcf-custom 送信ポートを使用して SAP システムにフラット ファイル IDOC を送信するためです。 どのような設定は、Wcf-custom 送信ポートに必要な詳細については、前に、まず vPrev 送信 IDOC のオーケストレーションに必要などのような物理ポートを理解する必要があります。  
  
- ファイルは、フラット ファイル IDOC を取得するポートを受信します。 このポートは、フラット ファイルを vPrev SAP アダプターを使用して生成されたスキーマ (BOMDOC01.xsd) に準拠した XML に変換するのに BizTalk アプリケーションで使用可能なフラット ファイル逆アセンブラー パイプラインを使用します。  
  
- VPrev SAP では、フラット ファイル IDOC を SAP システムに送信ポートを送信します。 フラット ファイルを送信する前に、ポートは、フラット ファイル アセンブラーを使用して XML IDOC フラット ファイル IDOC に変換します。  
  
  既存の vPrev BizTalk プロジェクトを移行するは、ファイルを変更する必要はありません受信ポートをフラット ファイル IDOC を取得し、フラット ファイル IDOC をフラット ファイル逆アセンブラーを使用して XML に変換します。 適切な構成設定で新しい Wcf-custom 送信ポートを構成する必要があるだけです。 このチュートリアルは、WCF ベースを使用して SAP システムに Idoc を送信する Wcf-custom 送信ポートを構成する方法を示します[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [手順 1: IDOC を送信するための vPrev BizTalk プロジェクトを構築して展開する](../../adapters-and-accelerators/adapter-sap/step-1-build-and-deploy-the-vprev-biztalk-project-for-sending-an-idoc.md)  
  
-   [手順 2: WCF-Custom の一方向の送信ポートを構成する](../../adapters-and-accelerators/adapter-sap/step-2-configure-a-wcf-custom-one-way-send-port.md)  
  
-   [手順 3: 移行されたアプリケーションをテストする](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application2.md)  
  
## <a name="see-also"></a>参照  
 [SAP アダプター チュートリアル](../../adapters-and-accelerators/adapter-sap/sap-adapter-tutorials.md)